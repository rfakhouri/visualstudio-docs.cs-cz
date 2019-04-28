---
title: Vytváření šablon projektu
ms.date: 01/02/2018
ms.topic: conceptual
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- project templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7cd5bd20d5840b560d5954d62e5d158eb1f6c6e6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62430507"
---
# <a name="how-to-create-project-templates"></a>Postupy: Vytváření šablon projektu

V tomto tématu se dozvíte, jak vytvořit šablonu pomocí **Průvodce exportem šablony**, která zabalí vaše šablony v *ZIP* souboru.

## <a name="use-the-export-template-wizard"></a>Pomocí Průvodce exportem šablony

1. Vytvoření projektu.

    > [!NOTE]
    > Při pojmenování projektu, který bude sloužit jako zdroj šablony, používejte pouze znaky platný identifikátor. V opačném případě kompilace může dojít k chybám v projektech, které jsou vytvořeny ze šablony. Další informace o platný identifikátor znacích naleznete v tématu [deklarované názvy elementu (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names) nebo [identifikátory (C++)](/cpp/cpp/identifiers-cpp). Alternativně můžete použít [parametry šablony](../ide/template-parameters.md) používat "bezpečné" názvy tříd a obory názvů.

2. Upravte projekt, dokud nebude připravený exportovat jako šablonu. Například můžete chtít upravit soubory kódu k označení, kde by měla probíhat náhrada parametru. Zobrazit [jak: Nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).

3. Na **projektu** nabídce zvolte **exportovat šablonu**.

   **Průvodce exportem šablony** otevře.

4. Na **zvolte typ šablony** stránce **šablonu projektu**. Vyberte projekt, který chcete exportovat do šablony a klikněte na tlačítko **Další**.

::: moniker range="vs-2017"

5. Na **vyberte možnosti šablony** stránky, zadejte název a volitelný popis, ikona a image ve verzi preview pro šablonu. Tyto položky se zobrazí v **nový projekt** dialogové okno. Zvolte **Dokončit**.

   Projekt se exportuje do *ZIP* soubor a umístí do zadané výstupní umístění a, k importu do sady Visual Studio.

Najít šablonu v **nový projekt** dialogového okna rozbalte **nainstalováno** a potom rozbalte kategorii, která odpovídá `ProjectType` element v *.vstemplate*souboru. Například *.vstemplate* soubor, který obsahuje `<ProjectType>CSharp</ProjectType>` se zobrazí v části **nainstalováno** > **Visual C#** , ve výchozím nastavení. Šablony můžete uspořádat do podadresáře typu projektu, stačí jim k vytvoření složky v tomto adresáři a uvedení do šablony *ZIP* soubor v ní. Další informace najdete v tématu [jak: Hledání a organizace šablon](../ide/how-to-locate-and-organize-project-and-item-templates.md).

::: moniker-end

::: moniker range=">=vs-2019"

5. Na **vyberte možnosti šablony** stránky, zadejte název a volitelný popis, ikona a image ve verzi preview pro šablonu. Tyto položky se zobrazí v dialogovém okně místo, kde můžete vytvořit nový projekt. Zvolte **Dokončit**.

   Projekt se exportuje do *ZIP* soubor a umístí do zadané výstupní umístění a, k importu do sady Visual Studio.

Pokud chcete najít šablony v dialogovém okně místo, kde můžete vytvořit nový projekt, ho vyhledat podle názvu nebo procházejte seznamem. (Filtrování založené na jazyce nebo typ projektu není nyní možné pro uživatelské šablony.)

::: moniker-end

## <a name="other-ways-to-create-project-templates"></a>Další způsoby vytváření šablon projektu

Šablony projektů můžete vytvořit ručně, shromažďování souborů, které tvoří projektu do složky a vytvořením *.vstemplate* soubor XML s příslušná metadata. Další informace najdete v tématu [jak: Ruční vytvoření webových šablon](../ide/how-to-manually-create-web-templates.md).

Pokud máte nainstalované Visual Studio SDK, můžete zabalit dokončená šablona v souboru VSIX pro nasazení pomocí **projekt VSIX** šablony. Další informace najdete v tématu [začít pracovat s šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).

## <a name="see-also"></a>Viz také:

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: Tvorba šablon položek](../ide/how-to-create-item-templates.md)
- [Začínáme s šablonou projektu VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)