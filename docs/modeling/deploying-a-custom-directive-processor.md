---
title: "Nasazení vlastního procesoru direktiv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, custom directive processors
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: be69cc9335480d901824ce8a4981728a34db6395
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="deploying-a-custom-directive-processor"></a>Nastavení vlastního procesoru direktiv

Pokud chcete použít vlastního procesoru direktiv v sadě Visual Studio na libovolném počítači, je nutné jej zaregistrovat pomocí jedné z metod popsaných v tomto tématu.  
  
Alternativní metody jsou následující:  
  
-   [Rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md). Tato metoda poskytuje způsob, jak nainstalovat a odinstalovat procesor direktiv ve vašem vlastním počítači i v jiných počítačích. Zpravidla můžete do stejného rozšíření VSIX zabalit jiné funkce.  
  
-   [VSPackage](../extensibility/internals/vspackages.md). Pokud definujete VSPackage obsahující kromě procesoru direktiv i jiné funkce, lze procesor direktiv pohodlně zaregistrovat.  
  
-   Nastavení klíče registru: Pomocí této metody přidáte položku registru pro procesor direktiv.  
  
Budete muset použít jednu z těchto metod, pouze pokud chcete k transformaci text šablony v sadě Visual Studio nebo MSBuild. Pokud ve své aplikaci používáte vlastního hostitele, je tento vlastní hostitel odpovědný za vyhledání procesoru direktiv pro jednotlivé direktivy.  
  
## <a name="deploying-a-directive-processor-in-a-vsix"></a>Nasazení procesoru direktiv v rozšíření VSIX

Můžete přidat do vlastního procesoru direktiv [rozšíření Visual Studio (VSIX)](../extensibility/starting-to-develop-visual-studio-extensions.md).
  
 Přitom musíte zajistit, aby v souboru .vsix byly obsaženy následující dvě položky:  
  
-   Sestavení (.dll), které obsahuje třídu vlastního procesoru direktiv  
  
-   Soubor .pkgdef, který registruje procesor direktiv Kořenový název tohoto souboru musí být stejný jako sestavení. Soubory mohou mít například název CDP.dll a CDP.pkgdef.  
  
Chcete-li zkontrolovat nebo změnit obsah souboru .vsix, změňte jeho příponu na .zip a pak jej otevřete. Po úpravě obsahu změňte příponu souboru zpět na .vsix.  

Soubor .vsix lze vytvořit několika způsoby. Jednu metodu popisuje následující postup.  

#### <a name="to-develop-a-custom-directive-processor-in-a-vsix-project"></a>Vývoj vlastního procesoru direktiv v projektu VSIX  
  
1.  Vytvoření projektu VSIX v sadě Visual Studio.  
  
    -   V **nový projekt** dialogové okno, rozbalte seznam **jazyka Visual Basic** nebo **Visual C#**, pak rozbalte **rozšiřitelnost**. Klikněte na tlačítko **projektu VSIX**.  
  
2.  V **source.extension.vsixmanifest**, nastavte typ obsahu a podporované edice.  
  
    1.  Ve VSIX manifest editoru na **prostředky** , zvolte **nový** a nastavte vlastnosti nové položky:  
  
         **Typ obsahu** = **VSPackage**  
  
         **Zdroj projektu** = \<*aktuálního projektu*>  
  
    2.  Klikněte na tlačítko **vybrané edice** a zkontrolujte typy instalace, na kterém chcete procesoru direktiv být použitelná.  
  
3.  Přidejte soubor .pkgdef a nastavte jeho vlastnosti, které mají být zahrnuty do rozšíření VSIX.  
  
    1.  Vytvořte textový soubor s názvem \< *assemblyName*> .pkgdef.  
  
         \<*assemblyName*> je většinou stejný jako název projektu.  
  
    2.  V Průzkumníku řešení ho vyberte a následujícím způsobem nastavte jeho vlastnosti:  
  
         **Akce sestavení** = **obsahu**  
  
         **Kopírovat do výstupního adresáře** = **vždy kopírovat**  
  
         **Zahrnout do VSIX** = **True**  
  
    3.  Nastavte název rozšíření VSIX a ujistěte se, že je ID jedinečné.  
  
4.  Do souboru .pkgdef přidejte následující text.  
  
    ```  
    [$RootKey$\TextTemplating]  
    [$RootKey$\TextTemplating\DirectiveProcessors]  
    [$RootKey$\TextTemplating\DirectiveProcessors\ CustomDirectiveProcessorName]  
    @="Custom Directive Processor description"  
    "Class"="NamespaceName.ClassName"  
    "CodeBase"="$PackageFolder$\AssemblyName.dll"  
    ```  
  
     Následující názvy nahraďte vlastní názvy: `CustomDirectiveProcessorName`, `NamespaceName`, `ClassName`, `AssemblyName`.  
  
5.  Přidejte do projektu následující odkazy:  
  
    -   **Microsoft.VisualStudio.TextTemplating.\*.0**  
  
    -   **Microsoft.VisualStudio.TextTemplating.Interfaces.\*.0**  
  
    -   **Microsoft.VisualStudio.TextTemplating.VSHost.\*.0**  
  
6.  Přidejte do projektu třídu vlastního procesoru direktiv.  
  
     Toto je veřejný třídu, která by měla implementovat <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> nebo <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
#### <a name="to-install-the-custom-directive-processor"></a>Instalace vlastního procesoru direktiv  
  
1.  V Průzkumníku Windows otevřete adresář sestavení (obvykle bin\Debug nebo bin\Release).  
  
2.  Pokud chcete procesor direktiv nainstalovat do jiného počítače, zkopírujte soubor .vsix do tohoto počítače.  
  
3.  Dvakrát klikněte na soubor .vsix. Instalační program rozšíření Visual Studio se zobrazí.  
  
4.  Restartujte sadu Visual Studio. Nyní budete moci spouštět textové šablony obsahující direktivy, které odkazují na vlastní procesor direktiv. Jednotlivé direktivy mají tento formát:  
  
     `<#@ CustomDirective Processor="CustomDirectiveProcessorName" parameter1="value1" ... #>`  
  
#### <a name="to-uninstall-or-temporarily-disable-the-custom-directive-processor"></a>Odinstalace nebo dočasné vypnutí vlastního procesoru direktiv  
  
1.  V sadě Visual Studio **nástroje** nabídky, klikněte na tlačítko **Správce rozšíření**.  
  
2.  Vyberte VSIX, který obsahuje procesoru direktiv a pak klikněte na tlačítko **odinstalace** nebo **zakázat**.  
  
### <a name="troubleshooting-a-directive-processor-in-a-vsix"></a>Řešení potíží s procesorem direktiv v rozšíření VSIX  
 Pokud procesor direktiv nefunguje, mohou vám pomoci následující návrhy:  
  
-   Název procesoru, který určíte v vlastní – direktiva by měl odpovídat `CustomDirectiveProcessorName` který jste zadali v souboru .pkgdef.  
  
-   Vaše `IsDirectiveSupported` metoda musí vrátit `true` když je předán název vaší `CustomDirective`.  
  
-   Pokud nevidíte rozšíření ve Správci rozšíření, ale systém nedovolí k jeho instalaci, odstranit rozšíření z **%localappdata%\Microsoft\VisualStudio\\\*. 0\Extensions\\** .  
  
-   Otevřete soubor .vsix a zkontrolujte jeho obsah. Chcete-li jej otevřít, změňte jeho příponu na .zip. Ověřte, zda obsahuje soubory .dll, .pkgdef a extension.vsixmanifest. Soubor extension.vsixmanifest by měl obsahovat příslušný seznam v uzlu SupportedProducts a měl by také obsahovat uzel VsPackage pod uzlem Content:  
  
     `<Content>`  
  
     `<VsPackage>CustomDirectiveProcessor.dll</VsPackage>`  
  
     `</Content>`  
  
## <a name="deploying-a-directive-processor-in-a-vspackage"></a>Nasazení procesoru direktiv v sadě VSPackage  
 Pokud je procesor direktiv součástí sady VSPackage, která se bude instalovat do mezipaměti GAC, můžete systém nechat vygenerovat soubor .pkgdef za vás.  
  
 Vložte do třídy balíčku následující atribut:  
  
```  
[ProvideDirectiveProcessor(typeof(DirectiveProcessorClass), "DirectiveProcessorName", "Directive processor description.")]  
```  
  
> [!NOTE]
>  Tento atribut je umístěn ve třídě balíčku, nikoli ve třídě procesoru direktiv.  
  
 Soubor .pkgdef se vygeneruje při sestavení projektu. Při instalaci sady VSPackage zaregistruje soubor .pkgdef procesor direktiv.  
  
 Ověřte, zda je soubor .pkgdef ve složce sestavení, obvykle bin\Debug nebo bin\Release. Pokud se nezobrazí, otevřete soubor .csproj v textovém editoru a odebrat následující uzel: `<GeneratePkgDefFile>false</GeneratePkgDefFile>`.  
  
 Další informace najdete v tématu [VSPackages](../extensibility/internals/vspackages.md).  
  
## <a name="setting-a-registry-key"></a>Nastavení klíče registru  
 Tato metoda instalace vlastního procesoru direktiv se příliš nedoporučuje. Neposkytuje totiž pohodlný způsob zapnutí a vypnutí procesoru direktiv ani způsob distribuce procesoru direktiv jiným uživatelům.  
  
> [!CAUTION]
>  Nesprávná úprava registru může vážně poškodit systém. Před prováděním změn registru nezapomeňte vytvořit zálohu všech cenných dat v počítači.  
  
#### <a name="to-register-a-directive-processor-by-setting-a-registry-key"></a>Registrace procesoru direktiv nastavením klíče registru  
  
1.  Run `regedit`.  
  
2.  V editoru registru přejděte na  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\\*.0\TextTemplating\DirectiveProcessors**  
  
     Pokud chcete nainstalovat procesoru direktiv experimentální verze sady Visual Studio, za "11.0" vložte "Exp".  
  
3.  Přidejte klíč registru, který má stejný název jako třída procesoru direktiv.  
  
    -   Ve stromu registru klikněte pravým tlačítkem myši **DirectiveProcessors** uzlu, přejděte na příkaz **nový**a potom klikněte na **klíč**.  
  
4.  V novém uzlu přidejte podle následujících tabulek řetězcové hodnoty Class a CodeBase nebo Assembly.  
  
    1.  Klikněte pravým tlačítkem na uzel, který jste vytvořili, přejděte na **nový**a potom klikněte na **řetězcovou hodnotu**.  
  
    2.  Upravte název hodnoty.  
  
    3.  Dvakrát klikněte na název a upravte data.  
  
 Pokud vlastní procesor direktiv není v mezipaměti GAC, měly by podklíče registru vypadat podle následující tabulky:  
  
|Název|Typ|Data|  
|----------|----------|----------|  
|(Výchozí)|REG_SZ|(hodnota nenastavena)|  
|Třída|REG_SZ|**\<Název Namespace >. \<Název třídy >**|  
|CodeBase|REG_SZ|**\<Cestu k >\\< název sestavení\>**|  
  
 Pokud je sestavení v mezipaměti GAC, měly by podklíče registru vypadat podle následující tabulky:  
  
|Název|Typ|Data|  
|----------|----------|----------|  
|(Výchozí)|REG_SZ|(hodnota nenastavena)|  
|Třída|REG_SZ|\<**Váš plně kvalifikovaný název třídy**>|  
|Assembly|REG_SZ|\<**Název sestavení v mezipaměti GAC**>|  
  
## <a name="see-also"></a>Viz také

[Vytváření vlastních procesorů pro direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md)