---
title: "Postupy: hledání a organizace projektů a šablon položek | Microsoft Docs"
ms.custom: 
ms.date: 06/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], locations
- custom template locations [Visual Studio]
- item templates, locations
- Visual Studio templates, locations
- project templates [Visual Studio], displaying
- templates [Visual Studio], locations
ms.assetid: 71f9ed52-c9c9-4818-9bce-c279ffaa0438
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1846b145833a7474e8662442313d0e39a262e67c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Postupy: Hledání a organizace projektů a šablon položek
Soubory šablony musí být umístěny v umístění, které Visual Studio rozpozná tak, aby se šablony zobrazí v **nový projekt** a **přidat novou položku** dialogová okna. Vlastní podkategorie šablon můžete vytvořit tak, aby podkategorií se také zobrazí v uživatelském rozhraní.  

## <a name="locating-templates"></a>Umístění šablon  
 Ve výchozím nastavení Visual Studio hledá dvě umístění pro šablony projektů a položek. Pokud komprimovaný soubor, který obsahuje soubor .vstemplate existuje v těchto umístěních, šablona se objeví v **nový projekt** nebo **přidat novou položku** dialogová okna.  

### <a name="installed-templates"></a>Nainstalovaných šablon  
 Ve výchozím nastavení šablony, které jsou nainstalované společně se sadou produktu jsou umístěny:  

-   \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\\*jazyk*\\*národní prostředí*\  

-   \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\\*jazyk*\\*národní prostředí\\*  

 Například na následující adresář obsahuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony projektu pro angličtinu:  

 C:\\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\VisualBasic\1033\  

### <a name="custom-templates"></a>Vlastní šablony  
 Ve výchozím nastavení vlastní šablony jsou umístěny:  

-   \My Documents\Visual studio *verze*\Templates\ProjectTemplates\\*jazyk*\  

-   \My Documents\Visual studio *verze*\Templates\ItemTemplates\\*jazyk*\  

 Například na následující adresář obsahuje vlastní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony projektu:  

 C:\Documents and Settings\UserName\My Documents\Visual Studio *verze*\Templates\ProjectTemplates\Visual C# \  

 Vlastní šablony neobsahují podadresáře pro lokalizované šablony. Můžete změnit výchozí adresář pro vlastní šablony na **možnosti** dialogovém **Environment\Projects a řešení**.  

## <a name="organizing-templates"></a>Uspořádání šablon  
 Kategorie v **nový projekt** a **přidat novou položku** dialogová okna odrážejí struktury adresářů, které existují v umístění nainstalovaných a vlastních šablon. Tyto struktury adresářů k organizování šablon způsobem, který vám vyhovuje, můžete upravit.  

> [!NOTE]
>  Nelze vytvořit novou kategorii úrovni programovací jazyk. Nové kategorie lze vytvořit pouze v rámci jednotlivé jazyky.  

 Pokud struktury adresářů pro nainstalované a vlastní šablony pro konkrétní jazyk nemají stejnou strukturu (to znamená, že zde je několik adresářů v jedné složce, které neexistují v jiné) souboru kategorií, které se zobrazují v **nový Projekt** dialogové okno bude spojení všech kategorií.  

### <a name="organizing-installed-templates"></a>Uspořádání nainstalovaných šablon  
 Nainstalovaných šablon můžete uspořádat tak, že vytvoříte podadresáře ve složce programovací jazyk. Tyto podsložky se zobrazí v **nový projekt** a **přidat novou položku** dialogová okna jako virtuální složky v rámci jednotlivé jazyky.  

##### <a name="to-create-new-installed-project-template-categories"></a>Vytvořit nový projekt nainstalované kategorie šablony  

1.  Vytvořte složku ve složce jazyka adresáře nainstalované šablony. Chcete-li například vytvořit kategorie Office pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony vytvoříte následující adresář projektu:  

     \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\VisualBasic\1033\Office\  

2.  Všechny šablony pro tuto kategorii umístěte do nové složky.  

3.  Zavřete všechny instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  Na **spustit** nabídky, klikněte na tlačítko **spustit**, typ **cmd**a klikněte na tlačítko **OK**.  

5.  Na příkazovém řádku, vyhledejte adresář, který obsahuje devenv.exe a zadejte **devenv/installvstemplates**.  

6.  Run [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

7.  Na **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **projektu**.  

8.  Ověřte, že kategorie Office se zobrazí v **nový projekt** dialogu **typy projektů** podokně v části [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)].  

 Můžete taky seskupit podmnožinu šablony položek projektu do vlastní složky.  

##### <a name="to-create-new-installed-item-template-categories"></a>Chcete-li vytvořit nový nainstalovány kategorie šablony položek  

1.  Vytvořte složku ve složce jazyka adresáře nainstalované šablony. Chcete-li například vytvořit webovou kategorii pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] položky šablony vytvoříte následující adresář:  

     \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\CSharp\1033\Web\  

2.  Všechny šablony pro tuto kategorii umístěte do nové složky.  

3.  Zavřete všechny instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  Na **spustit** nabídky, klikněte na tlačítko **spustit**, typ **cmd**a klikněte na tlačítko **OK**.  

5.  Na příkazovém řádku, vyhledejte adresář, který obsahuje devenv.exe a zadejte **devenv/Setup**.  

6.  Run [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

7.  Vytvořte projekt nebo otevřít existující projekt.  

8.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  

9. Ověřte, že webová kategorie zobrazuje v **přidat novou položku** dialogu **typy projektů** podokně.  

### <a name="organizing-custom-templates"></a>Uspořádání vlastních šablon  
 Vlastní šablony můžete uspořádat do vlastních kategorií přidáním nových složek v umístění vlastních šablon. **Nový projekt** dialogové okno odráží všechny změny kategorie šablony.  

##### <a name="to-create-new-custom-project-template-categories"></a>Vytvořit nový projekt vlastní kategorie šablony  

1.  Vytvořte složku ve složce jazyka v adresáři projektu vlastní šablony. Chcete-li například vytvořit HelloWorld kategorii pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony, vytvořili byste na následující adresář:  

     \My Documents\Visual studio *verze*\Templates\ProjectTemplates\CSharp\HelloWorld\  

2.  Všechny šablony pro tuto kategorii umístěte do nové složky.  

3.  Na **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **projektu**.  

4.  Ověřte, že kategorie HelloWorld zobrazuje v **nový projekt** dialogu **typy projektů** podokně v části [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].  

 Můžete taky seskupit podmnožinu vlastních šablon položek do vlastní složky.  

##### <a name="to-create-new-custom-item-template-categories"></a>Chcete-li vytvořit nové vlastní položky kategorie šablon  

1.  Vytvořte složku ve složce jazyka v adresáři šablony vlastní položky. Chcete-li například vytvořit HelloWorld kategorii pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablony vytvoříte následující adresář:  

     \My Documents\Visual studio *verze*\Templates\ItemTemplates\CSharp\HelloWorld\  

2.  Všechny šablony pro tuto kategorii umístěte do nové složky.  

3.  Vytvořte projekt nebo otevřít existující projekt.  

4.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  

5.  Ověřte, že kategorie HelloWorld zobrazuje v **přidat novou položku** dialogu **typy projektů** podokně.  

### <a name="displaying-templates-in-parent-categories"></a>Zobrazení šablony v nadřazené kategorie  
 Můžete povolit šablony v podkategorie, který se má zobrazit ve svých nadřazených kategoriích pomocí `NumberOfParentCategoriesToRollUp` element v souboru .vstemplate. Tyto kroky jsou identické šablony projektů a šablon položek.  

##### <a name="to-display-templates-in-parent-categories"></a>Chcete-li zobrazit šablony v nadřazené kategorie  

1.  Vyhledejte soubor .zip, který obsahuje šablony.  

2.  Rozbalte soubor .zip.  

3.  Otevřete soubor .vstemplate v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  V `TemplateData` elementu, přidejte `NumberOfParentCategoriesToRollUp` elementu. Například následující kód vytvoří šablonu viditelné v nadřazené kategorie, ale ne vyšší.  

    ```  
    <TemplateData>  
        ...  
        <NumberOfParentCategoriesToRollUp>  
            1  
        </NumberOfParentCategoriesToRollUp>  
        ...  
    </TemplateData>  
    ```  

5.  Uložte a zavřete soubor .vstemplate.  

6.  Vyberte soubory v šabloně, klikněte pravým tlačítkem na výběr, klikněte na **odeslat**a potom klikněte na **komprimované složky (ZIP)**. Soubory jsou komprimovány do souboru ZIP.  

7.  Odstraňte extrahované soubory šablony a původní soubor .zip šablony.  

8.  Uveďte nový soubor ZIP do adresáře, který byl odstraněný .zip soubor.  

## <a name="see-also"></a>Viz také  
 [Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [NumberOfParentCategoriesToRollUp (šablony sady Visual Studio)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)   
 [Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)   
 [Postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md)
