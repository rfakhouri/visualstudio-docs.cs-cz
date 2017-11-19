---
title: "Nasazení vlastní spuštění stránky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package start page
- deploy start page
ms.assetid: 4a7eb360-de83-41d5-be53-3cfb160d19f9
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b2217b77116ea561c32e96fcb7b92b520e680025
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="deploying-custom-start-pages"></a>Nasazení vlastní úvodní stránky
Vlastní spuštění stránky můžete nasadit pomocí VSIX nasazení nebo kopírování souborů do správných umístění na cílovém počítači.  
  
## <a name="vsix-deployment-by-using-the-start-page-project-template"></a>VSIX nasazení pomocí šablony projektu stránka Start  
 Při vytváření – úvodní stránka pomocí šablony projektu – úvodní stránka a následně vytvořit projekt, Visual Studio vytvoří soubor VSIX, které můžete distribuovat. Balení – úvodní stránka v soubor VSIX poskytuje následující možnosti pro nasazení, v závislosti na vaší cílová skupina:  
  
-   Ve sdílené síťové složce nebo na veřejný web můžete umístit soubor VSIX. Když uživatel otevře soubor, automaticky se nainstaluje stránce Start.  
  
-   Můžete nahrát soubor VSIX [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webové lokality tak, aby uživatelé můžete nainstalovat pomocí **Správce rozšíření**.  
  
 Šablona projektu – úvodní stránka vytvoří kopii výchozí Visual Studio – úvodní stránka, takže můžete upravit kopie a zachovat původní.  
  
 Šablona projektu – úvodní stránka můžete získat pomocí **Správce rozšíření** nebo stažením z webu.  
  
## <a name="vsix-deployment-without-using-the-start-page-project-template"></a>VSIX nasazení bez použití šablony úvodní stránku projektu  
 Úspěšné nasazení VSIX vyžaduje rozšíření má být nainstalován do složky, které jsou rozpoznány registraci v VSIX a nástrojem **Správce rozšíření**. Vzhledem k tomu, že šablona projektu – úvodní stránka již Určuje správné složky, doporučujeme pracovat pokaždé, když chcete balíček rozšíření pro nasazení VSIX. Pokud máte případ, kdy nelze použít šablonu, můžete však vytvořit VSIX nasazení bez použití.  
  
 Vytvoření nasazení VSIX bez pomocí šablony projektu – úvodní stránka, nejprve vytvořte soubor VSIX pro úvodní stránku v některém z těchto dvou způsobů:  
  
-   Můžete přidat vlastní soubory – úvodní stránka ke prázdný projekt VSIX. Další informace najdete v tématu [šablona projektu VSIX](../extensibility/vsix-project-template.md).  
  
-   Tím, že ručně vytvoříte soubor VSIX. Chcete-li vytvořit soubor VSIX ručně:  
    
    1.  Vytvořte soubor extension.vsixmanifest a souboru .xml [Content_Types] do nové složky. Další informace najdete v tématu [anatomie balíčku VSIX](/visualstudio/extensibility/anatomy-of-a-vsix-package).  
  
    2.  V Průzkumníku Windows klikněte pravým tlačítkem na složku, která obsahuje dva soubory XML, klikněte na tlačítko Odeslat a klikněte na položku komprimované složky. Přejmenujte výsledný soubor ZIP Filename.vsix, kde název souboru je název souboru redistributable, který nainstaluje vašeho balíčku.  
  
 Pro sadu Visual Studio – úvodní stránka rozpoznat `Content Element` VSIX manifestu musí obsahovat `CustomExtension Element` který má `Type` atribut nastaven na `"StartPage"`. Úvodní stránka rozšíření, která byla nainstalována pomocí VSIX nasazení se zobrazí v **přizpůsobení úvodní stránka** seznam na **spuštění** možnosti stránky jako **[nainstalovaná rozšíření]** *Název rozšíření*.  
  
 Pokud váš balíček – úvodní stránka obsahuje sestavení, je nutné přidat vazby cesta registrace, aby byly k dispozici při spuštění sady Visual Studio. K tomu, ujistěte se, že váš balíček obsahuje soubor .pkgdef, který obsahuje následující informace.  
  
```  
[$RootKey$\BindingPaths\{Insert a new GUID here}]  
"$PackageFolder$"=""  
```  
  
### <a name="vsix-deployment-for-all-users"></a>VSIX nasazení pro všechny uživatele  
 Ve výchozím nastavení rozšíření nasazené v VSIX balíčky nainstalovat pouze pro aktuálního uživatele. Úvodní stránka instalace pro všechny uživatele cílovém počítači můžete nastavit tak, že vytvoříte nasazení s všichni uživatelé.  
  
##### <a name="to-create-an-all-users-deployment"></a>Pro vytvoření nasazení všichni uživatelé  
  
1.  Otevřete soubor extension.vsixmanifest v zobrazení kódu.  
  
2.  V `Identifier` element manifestu vsix, přidejte `AllUsers` element, který má hodnotu `true`.  
  
    ```  
    <AllUsers>true</AllUsers>  
    ```  
  
     To způsobí, že instalační program vsix vyzvat, aby oprávnění správce, a potom nainstalovat soubory na \Common7\IDE\Extensions.  
  
3.  Otevřete soubor .pkgdef.  
  
4.  Upravit .pkgdef nastavit výchozí úvodní stránku v rámci HKLM přidáním následující příkaz, kde *MyStartPage.xaml* je název souboru XAML, který obsahuje vaše stránky Start.  
  
     [$RootKey$ \StartPage\Default]  
  
     "Uri"="$PackageFolder$\\*MyStartPage.xaml*"  
  
     Tato hodnota informuje Visual v platnosti do nového umístění – úvodní stránka.  
  
## <a name="file-copy-deployment"></a>Nasazení pomocí kopírování souborů  
 Nemáte k vytvoření soubor VSIX nasadit vlastní úvodní stránku. Místo toho můžete zkopírovat kód a podpůrné soubory přímo do složky \StartPages\ uživatele. **Přizpůsobení úvodní stránka** na seznamu **spuštění** stránka Možnosti seznam všech souborů XAML v této složce, společně s cestou k – například %USERPROFILE%\My Documents\Visual Studio  *verze*\StartPages\\*název souboru*XAML. Pokud vaše – úvodní stránka obsahuje odkazy na sestavení privátní, musíte je zkopírovat a vložit je ve složce \PrivateAssemblies\.  
  
 K distribuci úvodní stránku, kterou jste vytvořili bez balení v soubor VSIX doporučujeme použít strategie kopie základní soubor například dávkový skript nebo jiné technologie nasazení, které vám umožní chápat soubory požadované adresáře.  
  
#### <a name="to-manually-install-a-custom-start-page"></a>Při ruční instalaci vlastní úvodní stránku  
  
1.  Souboru XAML, který obsahuje kód, – úvodní stránka, spolu s všechny podpůrné soubory než sestavení, zkopírujte a vložte je do složky \StartPages\ uživatele.  
  
2.  Pokud stránka Start vyžaduje sestavení, je zkopírujte a vložte je do... \\ *Instalační složka nástroje visual Studio*\Common7\IDE\PrivateAssemblies\\.  
  
3.  V **přizpůsobení úvodní stránka** na seznamu **spuštění** možnosti vyberte Nová stránka Start. Další informace najdete v tématu [přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md)   
 [Přidání uživatelského ovládacího prvku do úvodní stránky](../extensibility/adding-user-control-to-the-start-page.md)