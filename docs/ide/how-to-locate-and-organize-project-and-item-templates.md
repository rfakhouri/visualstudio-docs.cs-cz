---
title: Vyhledání šablon
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: db74d23cf42e371f00bf25c7edcd8c480f7649d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62430273"
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Postupy: Hledání a organizace šablon projektů a položek

Soubory šablony musí být umístěn v zadaném umístění je zobrazený nový projekt a dialogová okna Nová položka...

::: moniker range="vs-2017"

Můžete také vytvořit vlastní podkategorie v umístění uživatelské šablony a kategorie jsou uvedeny v **nový projekt** a **přidat novou položku** dialogových oknech.

::: moniker-end

## <a name="locate-templates"></a>Vyhledání šablon

Nainstalované šablony a uživatelské šablony jsou uloženy ve dvou různých umístěních.

### <a name="installed-templates"></a>Nainstalované šablony

Ve výchozím nastavení jsou součástí šablony, které instalace sady Visual Studio:

::: moniker range="vs-2017"

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2017\\\<edition>\\Common7\IDE\ProjectTemplates\\<Language\>\\<Locale ID\>*

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2017\\\<edition>\Common7\IDE\ItemTemplates\\<Language\>\\<Locale ID\>*

Například následující adresář má položku šablony jazyka Visual Basic pro angličtinu (LCID 1033):

*C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\Common7\\IDE\\ItemTemplates\\VisualBasic\\1033*

::: moniker-end

::: moniker range=">=vs-2019"

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\\<edition>\\Common7\IDE\ProjectTemplates\\<Language\>\\<Locale ID\>*

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\\<edition>\Common7\IDE\ItemTemplates\\<Language\>\\<Locale ID\>*

Například následující adresář má položku šablony jazyka Visual Basic pro angličtinu (LCID 1033):

*C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Community\\Common7\\IDE\\ItemTemplates\\VisualBasic\\1033*

::: moniker-end

### <a name="user-templates"></a>Uživatelské šablony

Pokud chcete přidat komprimované (*ZIP*) soubor, který obsahuje *.vstemplate* soubor do adresáře šablon, uživatele, se šablona zobrazuje v nový projekt a dialogová okna nové položky. Ve výchozím nastavení uživatelské šablony jsou umístěny v:

::: moniker range="vs-2017"

- *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates*

Například následující adresář má uživatel šablony projektů pro C#:

- *C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\VisualC#*

::: moniker-end

::: moniker range=">=vs-2019"

- *%USERPROFILE%\Documents\Visual Studio 2019\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual Studio 2019\Templates\ItemTemplates*

Například následující adresář má uživatel šablony projektů pro C#:

- *C:\Users\UserName\Documents\Visual Studio 2019\Templates\ProjectTemplates\Visual C#*

::: moniker-end

> [!TIP]
> Můžete změnit umístění známé uživatelské šablony v **nástroje** > **možnosti** > **projekty a řešení**  >   **Umístění**.

::: moniker range="vs-2017"

## <a name="organize-templates"></a>Organizace šablon

Kategorie v **nový projekt** a **přidat novou položku** dialogová okna, aby odrážely struktury adresářů, které existují v umístění šablon nainstalovaných šablony a uživatele. Uživatelské šablony lze uspořádat do své vlastní kategorie tak, že přidáte nové složky do šablony adresáře uživatele. **Nový projekt** a **přidat novou položku** dialogová okna zobrazit změny provedené kategorie šablony uživatele.

> [!NOTE]
> Nelze vytvořit novou kategorii na úrovni programovací jazyk. Nové kategorie lze vytvořit pouze v rámci jednotlivé jazyky.

### <a name="create-new-user-project-template-categories"></a>Vytvoření nového projektu uživatele kategorií šablon

1. Vytvořte složku ve složce programovací jazyk v adresáři projektu šablony uživatele. Například chcete navázat **HelloWorld** kategorii pro C# šablony projektů, vytvořte následující adresář:

    - *\%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates\Visual C#\HelloWorld*

1. Umístěte všechny šablony pro tuto kategorii do nové složky.

1. Na **souboru** nabídce zvolte **nový** > **projektu**.

   **HelloWorld** se zobrazí kategorie **nový projekt** dialogovém okně **nainstalováno** > **Visual C#** .

### <a name="create-new-user-item-template-categories"></a>Vytvořit novou položku uživatele kategorií šablon

1. Vytvořte složku ve složce programovací jazyk v adresář šablon položek uživatele. Například chcete navázat **HelloWorld** kategorii pro C# šablon položek, vytvořte následující adresář:

    - *\%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ItemTemplates\Visual C#\HelloWorld*

1. Umístěte všechny šablony pro tuto kategorii do nové složky.

1. Vytvoření projektu nebo otevřete existující projekt. Potom na **projektu** nabídce zvolte **přidat novou položku**.

   **HelloWorld** se zobrazí kategorie **přidat novou položku** dialogovém okně **nainstalováno** > **Visual C# položky**.

### <a name="display-templates-in-parent-categories"></a>Zobrazení šablony v nadřazené kategorie

Můžete povolit v podkategoriích, který se má zobrazit v jejich nadřazené kategorie pomocí šablony `NumberOfParentCategoriesToRollUp` prvek *.vstemplate* souboru. Tyto kroky jsou stejné pro šablony projektů a šablon položek.

1. Vyhledejte *ZIP* soubor, který obsahuje šablonu.

1. Extrahovat *ZIP* souboru.

1. Otevřít *.vstemplate* souboru v sadě Visual Studio.

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

1. Uložte a zavřete *.vstemplate* souboru.

1. Vyberte soubory do šablony, klikněte pravým tlačítkem na výběr a zvolte **odeslat** > **komprimovanou složku (ZIP)**.

   Soubory jsou komprimované do *ZIP* souboru.

1. Odstranit extrahované soubory šablony a starou šablonu *ZIP* souboru.

1. Vložit nový *ZIP* v adresáři, který měl na odstraněný soubor *ZIP* souboru.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Visual Studio odkaz na schéma šablon (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md)
- [NumberOfParentCategoriesToRollUp (šablony sady Visual Studio)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)
- [Postupy: Vytváření šablon projektu](../ide/how-to-create-project-templates.md)
- [Postupy: Tvorba šablon položek](../ide/how-to-create-item-templates.md)