---
title: 'Postupy: Vytvoření. Vsct soubor | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a2483c000bb7c9446ac51bb94ef4006a7b2ac89f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056936"
---
# <a name="how-to-create-a-vsct-file"></a>Postupy: Vytvoření souboru .Vsct
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Existuje několik způsobů, jak vytvořit soubor konfigurace (.vsct) založený na formátu XML tabulky příkazů aplikace Visual Studio.  
  
- Můžete vytvořit nový balíček VSPackage správy kódu v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] balíčku šablony.  
  
- Konfigurace kompilátoru tabulky příkaz založený na formátu XML, Vsct.exe, můžete použít vygenerovat soubor z existujícího souboru .ctc.  
  
- Vsct.exe můžete použít ke generování souboru .vsct z existujícího souboru .cto.  
  
- Můžete ručně vytvořit nový soubor .vsct.  
  
  Toto téma vysvětluje postup ručního vytvoření nového souboru .vsct.  
  
### <a name="to-manually-create-a-new-vsct-file"></a>Ruční vytvoření nového souboru .vsct  
  
1. Spustit [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
2. Na **souboru** nabídky, přejděte k **nový**a potom klikněte na tlačítko **souboru**.  
  
3. V **šablony** podokně klikněte na tlačítko **soubor XML** a potom klikněte na tlačítko **otevřít**.  
  
4. Na **zobrazení** nabídky, klikněte na tlačítko **okno vlastností** zobrazíte vlastnosti souboru XML.  
  
5. V **vlastnosti** okna, klikněte na tlačítko Procházet (...) na vlastnost schémat.  
  
6. V seznamu schémata XSD vyberte schéma vsct.xsd. Pokud to není v seznamu, klikněte na tlačítko **přidat** a pak vyhledejte soubor na místním disku. Klikněte na tlačítko **OK** až budete hotoví.  
  
7. V souboru XML, zadejte `<CommandTable` a potom stiskněte klávesu TAB. Zavřete značku zadáním `>`.  
  
     Tím se vytvoří soubor základní .vsct.  
  
8. Vyplňte elementy souboru XML, který chcete přidat, podle [schématu VSCT](../../extensibility/vsct-xml-schema-reference.md). Další informace najdete v tématu [vytváření obsahu. Soubory Vsct](../../extensibility/internals/authoring-dot-vsct-files.md)  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Pouhým přidáním souboru .vsct do projektu nezpůsobí, je pro kompilaci. Musí obsahovat ho v procesu sestavení.  
  
### <a name="to-add-a-vsct-file-to-project-compilation"></a>Přidat do projektu kompilace souboru .vsct  
  
1. Otevřete soubor projektu v editoru. Pokud projekt načíst, musí se nejdřív uvolnit.  
  
2. Přidat [itemgroup – element](../../msbuild/itemgroup-element-msbuild.md) , který obsahuje VSCTCompile element, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="TopLevelMenu.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
  
    ```  
  
     ResourceName element musí být vždy nastavená na `Menus.ctmenu`.  
  
3. Pokud váš projekt obsahuje soubor RESX, přidejte EmbeddedResource element, který obsahuje MergeWithCTO element, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <ManifestResourceName>VSPackage</ManifestResourceName>  
    </EmbeddedResource>  
  
    ```  
  
     Tento kód by měl přejít uvnitř itemgroup – element, který obsahuje vložené prostředky.  
  
4. Otevřete soubor balíčku, obvykle s názvem *ProjectName*Package.cs nebo *ProjectName*Package.vb v editoru.  
  
5. Přidejte atribut ProvideMenuResource do třídy balíčku, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    ```  
  
     První hodnota parametru musí odpovídat hodnotě atributu ResourceName, který jste definovali v souboru projektu.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření obsahu. Soubory Vsct](../../extensibility/internals/authoring-dot-vsct-files.md)   
 [Tabulky příkazů sady Visual Studio (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Postupy: Vytvoření. Vsct soubor z existující. Soubor CTC](../../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file.md)   
 [Postupy: Vytvoření. Vsct soubor z existující. Soubor technický ředitel](../../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file.md)   
 [XML schéma VSCT – referenční informace](../../extensibility/vsct-xml-schema-reference.md)
