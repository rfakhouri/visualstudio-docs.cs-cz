---
title: "Postupy: vytvoření. Soubor Vsct | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f05461aa75a8088f758bd24ec5e73ccd407a8681
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-vsct-file"></a>Postupy: vytvoření. Soubor Vsct  
  
Existuje několik způsobů, jak vytvořit soubor konfigurace (.vsct) na základě XML Visual Studio příkaz tabulky.  
  
-   Můžete vytvořit nové VSPackage v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] balíčku šablony.  
  
-   Konfigurace kompilátoru tabulka příkazu založeného na XML, Vsct.exe, můžete použít ke generování souboru z existující soubor .ctc.  
  
-   Můžete generovat soubor .vsct z existující soubor .cto Vsct.exe.  
  
-   Můžete ručně vytvořit nový soubor .vsct.  
  
 Toto téma vysvětluje, jak ručně vytvořit nový soubor .vsct.  
  
### <a name="to-manually-create-a-new-vsct-file"></a>Ruční vytvoření nového souboru .vsct  
  
1.  Spustit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **soubor**.  
  
3.  V **šablony** podokně klikněte na tlačítko **souboru XML** a pak klikněte na **otevřete**.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **vlastnosti – okno** zobrazíte vlastnosti souboru XML.  
  
5.  V **vlastnosti** okně klikněte na tlačítko Procházet (...) pro vlastnost schémat.  
  
6.  V seznamu XSD schémata vyberte schéma vsct.xsd. Pokud není v seznamu, klikněte na tlačítko **přidat** a pak vyhledejte soubor na místním disku. Klikněte na tlačítko **OK** po dokončení.  
  
7.  V souboru XML zadejte `<CommandTable` a potom stiskněte klávesu TAB. Zavřete značku zadáním `>`.  
  
     Tím se vytvoří soubor základní .vsct.  
  
8.  Vyplňte elementy souboru XML, který chcete přidat, podle [VSCT schématu](../../extensibility/vsct-xml-schema-reference.md). Další informace najdete v tématu [vytváření obsahu. Vsct soubory](../../extensibility/internals/authoring-dot-vsct-files.md)  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Postupy: vytvoření. Soubor Vsct z existující. CTC souboru  
  
Soubor formátu XML .vsct můžete vytvořit z existující soubor zdroje tabulky .ctc příkaz. Díky tomu můžete využít výhod nového formátu XML [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] formátu kompilátoru příkaz tabulky (VSCT).  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Vytvořte soubor .vsct ze souboru .ctc  
  
1.  Získejte kopii souboru Perl jazyk.  
  
2.  Získejte kopii souboru skriptu Perl ConvertCTCToVSCT.pl, obvykle nachází v  *\<cesta instalace Visual Studio SDK >*\VisualStudioIntegration\Tools\bin složky.  
  
3.  Získejte kopii souboru .ctc zdrojový soubor, který chcete převést.  
  
4.  Soubory umístíte do stejného adresáře.  
  
5.  V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] okna příkazového řádku, přejděte do adresáře.  
  
6.  Typ  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     kde PkgCmd.ctc je název souboru .ctc a PkgCmd.vsct je název souboru .vsct, který chcete vytvořit.  
  
     Tím se vytvoří nové tabulky zdrojového souboru příkaz XML .vsct. Soubor můžete zkompilovat pomocí Vsct.exe, kompilátor VSCT, stejně jako jakýkoli jiný soubor .vsct.  
  
    > [!NOTE]
    >  Můžete zlepšit čitelnost souboru .vsct přeformátování komentáře XML.  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>Postupy: vytvoření. Soubor Vsct z existující. Soubor technického ředitele  
  
Můžete vytvořit soubor .vsct na základě XML z existujícího souboru binární .cto. To umožňuje využít výhod nový formát kompilátoru příkaz tabulky. Tento proces funguje i v případě, že soubor .cto byl kompilován ze souboru .ctc. Můžete upravit a kompilovat .vsct soubor do jiného souboru .cto.  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>Vytvořte soubor .vsct ze souboru .cto  
  
1.  Získáte kopie .cto souboru a jeho odpovídající soubor .ctsym.  
  
2.  Soubory umístíte do stejného adresáře jako vsct.exe kompilátoru.  
  
3.  V aplikaci Visual Studio příkazovém řádku přejděte do adresáře, který obsahuje soubory .cto a .ctsym.  
  
4.  Typ **vsct.exe** *ctofilename***.cto** *vsctfilename***.vsct -S**  *symfilename***.ctsym**.  
  
     `ctofilename`je název souboru .cto `vsctfilename` je název souboru vsct, kterou chcete vytvořit, a `symfilename` je název souboru .ctsym.  
  
     Tento proces vytvoří novou tabulku kompilátoru soubor příkaz XML .vsct. Můžete upravit a kompilaci souboru s vsct.exe, vsct kompilátoru, stejně jako jakýkoli jiný soubor .vsct.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Stačí přidat do projektu soubor .vsct nezpůsobí, se pro kompilaci. V procesu sestavení musí obsahovat ho.  
  
### <a name="to-add-a-vsct-file-to-project-compilation"></a>Přidání souboru .vsct do projektu kompilace  
  
1.  V editoru otevřete soubor projektu. Pokud projekt je načtena, musíte ji nejprve uvolnit.  
  
2.  Přidat [ItemGroup – element](../../msbuild/itemgroup-element-msbuild.md) VSCTCompile element, který obsahuje jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="TopLevelMenu.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
  
    ```  
  
     ResourceName element musí být vždy nastavená na `Menus.ctmenu`.  
  
3.  Pokud projekt obsahuje soubor .resx, přidejte EmbeddedResource elementu, který obsahuje MergeWithCTO element, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <ManifestResourceName>VSPackage</ManifestResourceName>  
    </EmbeddedResource>  
  
    ```  
  
     Tento kód by měl přejděte do ItemGroup elementu, který obsahuje vložené prostředky.  
  
4.  Otevřete soubor balíčku, obvykle s názvem *ProjectName*Package.cs nebo *ProjectName*Package.vb v editoru.  
  
5.  Přidáte atribut ProvideMenuResource k třídě balíček, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    ```  
  
     První hodnota parametru musí shodovat s hodnotou ResourceName atributu, který jste zadali v souboru projektu.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření obsahu. Vsct soubory](../../extensibility/internals/authoring-dot-vsct-files.md)   
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Referenční dokumentace schématu VSCT XML](../../extensibility/vsct-xml-schema-reference.md)