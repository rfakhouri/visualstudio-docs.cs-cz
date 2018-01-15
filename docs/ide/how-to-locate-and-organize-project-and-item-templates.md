---
title: "Organizace šablon v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
- Visual Studio templates, organizing
- templates [Visual Studio], organizing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c58bda5570be9cdb7fba7a8f90a282df7b7167a2
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Postupy: hledání a organizace šablon projektů a položek

Soubory šablony musí být umístěny v umístění, které rozpozná, šablon, aby se zobrazí v sadě Visual Studio **nový projekt** a **přidat novou položku** dialogová okna. Můžete také vytvořit vlastní podkategorie v šabloně umístění uživatele a kategorie se zobrazují v **nový projekt** a **přidat novou položku** dialogová okna.

## <a name="locate-templates"></a>Najděte šablony

Nainstalované šablony a uživatele jsou uloženy ve dvou různých umístěních.

### <a name="user-templates"></a>Uživatelské šablony

Pokud přidáte soubor komprimované (.zip), který obsahuje soubor .vstemplate k adresáři uživatele šablony, zobrazí se v **nový projekt** nebo **přidat novou položku** dialogové okno. Ve výchozím nastavení jsou umístěny uživatelské šablony v:

- %USERPROFILE%\Documents\Visual studio \<verze\>\Templates\ProjectTemplates

- %USERPROFILE%\Documents\Visual studio \<verze\>\Templates\ItemTemplates

Například na následující adresář obsahuje šablony projektů uživatele pro jazyk C#:

   C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C# \

> [!TIP]
> Můžete nastavit umístění uživatele šablon v **nástroje** > **možnosti** > **projekty a řešení**  >   **Umístění**.

### <a name="installed-templates"></a>Nainstalovaných šablon

Ve výchozím nastavení šablony nainstalované pomocí sady Visual Studio se nacházejí v:

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\\*programovací jazyk*\\*ID národního prostředí*

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\\*programovací jazyk*\\*ID národního prostředí*

Například na následující adresář obsahuje šablony položek jazyka Visual Basic pro angličtinu (LCID 1033):

   C:\\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\VisualBasic\1033\

## <a name="organize-templates"></a>Organizace šablon

Kategorie v **nový projekt** a **přidat novou položku** dialogová okna odrážejí struktury adresářů, které existují v umístění šablony nainstalované šablony a uživatele. Šablony uživatele můžete uspořádat do vlastních kategorií přidáním nových složek do adresáře uživatelů šablony. **Nový projekt** a **přidat novou položku** dialogová okna odráží všechny změny kategorie šablony uživatele.

> [!NOTE]
> Nelze vytvořit novou kategorii úrovni programovací jazyk. Nové kategorie lze vytvořit pouze v rámci jednotlivé jazyky.

### <a name="to-create-new-user-project-template-categories"></a>Vytvořit nového uživatele kategorie šablony projektu

1. Vytvořte složku ve složce programovací jazyk v adresáři uživatele projektu šablony. Chcete-li například vytvořit **HelloWorld** kategorii pro C# šablony projektů, vytvořte na následující adresář:

    \%USERPROFILE%\Documents\Visual Studio \<verze\>\HelloWorld\ \Templates\ProjectTemplates\Visual C#

1. Všechny šablony pro tuto kategorii umístěte do nové složky.

1. Na **soubor** nabídce zvolte **nový** > **projektu**.

   **HelloWorld** kategorie se zobrazí v **nový projekt** dialogovém **nainstalovaná** > **Visual C#**.

### <a name="to-create-new-user-item-template-categories"></a>Chcete-li vytvořit nového uživatele kategorie šablony položek

1. Vytvořte složku ve složce programovací jazyk v adresáři uživatele položky šablony. Chcete-li například vytvořit **HelloWorld** kategorii pro C# šablony položek, vytvořte na následující adresář:

    \%USERPROFILE%\Documents\Visual Studio \<verze\>\HelloWorld\ \Templates\ItemTemplates\Visual C#

1. Všechny šablony pro tuto kategorii umístěte do nové složky.

1. Vytvořte projekt nebo otevřít existující projekt. Potom na **projektu** nabídce zvolte **přidat novou položku**.

   **HelloWorld** kategorie se zobrazí v **přidat novou položku** dialogovém **nainstalovaná** > **Visual C# položky**.

### <a name="display-templates-in-parent-categories"></a>Zobrazit šablony v nadřazené kategorie

Můžete povolit šablony v podkategorie, který se má zobrazit ve svých nadřazených kategoriích pomocí `NumberOfParentCategoriesToRollUp` element v souboru .vstemplate. Tyto kroky jsou identické šablony projektů a šablon položek.

#### <a name="to-display-templates-in-parent-categories"></a>Chcete-li zobrazit šablony v nadřazené kategorie

1. Vyhledejte soubor .zip, který obsahuje šablony.

1. Rozbalte soubor .zip.

1. Otevřete soubor .vstemplate v sadě Visual Studio.

1. V `TemplateData` elementu, přidejte `NumberOfParentCategoriesToRollUp` elementu. Například následující kód vytvoří šablonu viditelné v nadřazené kategorie, ale ne vyšší.

    ```xml
    <TemplateData>
        ...
        <NumberOfParentCategoriesToRollUp>
            1
        </NumberOfParentCategoriesToRollUp>
        ...
    </TemplateData>
    ```

1. Uložte a zavřete soubor .vstemplate.

1. Vyberte soubory v šabloně, klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**.

   Soubory jsou komprimovány do souboru ZIP.

1. Odstraňte extrahované soubory šablony a původní soubor .zip šablony.

1. Uveďte nový soubor ZIP do adresáře, který byl odstraněný .zip soubor.

## <a name="see-also"></a>Viz také

[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Odkaz na schéma šablon sady Visual Studio (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)  
[NumberOfParentCategoriesToRollUp (šablony sady Visual Studio)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)  
[Postupy: Vytváření šablon projektu](../ide/how-to-create-project-templates.md)  
[Postupy: Vytváření šablon položek](../ide/how-to-create-item-templates.md)
