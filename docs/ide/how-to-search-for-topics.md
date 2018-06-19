---
title: 'Postupy: vyhledávání témat'
ms.date: 11/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
ms.assetid: 683f1b0c-1551-4bba-91fe-3855f03fdd69
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 157d081b5bc67fed37246f50607d7d2a4efaf9c0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945594"
---
# <a name="how-to-search-for-topics"></a>Postupy: vyhledávání témat

Najít všechna témata, které obsahují určité slovo můžete použít funkci fulltextového vyhledávání. Také můžete upřesnit a přizpůsobit hledání pomocí zástupných znaků výrazy, logické operátory a operátory rozšířeného vyhledávání.

Otevřete **vyhledávání** , zvolte **vyhledávání** ve **Help Viewer** okno, nebo pokud se uživatel klávesnice, zvolte **Ctrl** + **E**.

## <a name="to-perform-a-full-text-search"></a>K provedení fulltextové vyhledávání

1.  Do vyhledávacího pole zadejte slovo, které chcete najít.

2.  Vyhledávací dotaz zadejte které operátory logických nebo rozšířeného vyhledávání chcete použít pro vyhledávání, pokud existuje. Vyhledat všechny dostupnou nápovědu, nepoužívejte operátory.

    > [!NOTE]
    > V **možnosti prohlížeče** dialogové okno, můžete zadat další předvolby, třeba maximální počet výsledků hledání pro zobrazení na čas a jestli se mají zahrnout obsah v angličtině, pokud vaše primární národního prostředí není angličtina.

3.  Vyberte **Enter** klíč.

     Vyhledávání vrací maximálně 200 přístupů, ve výchozím nastavení a zobrazí je v oblasti Výsledky hledání. Další informace o verzi pro každý výsledek se může zobrazit v závislosti na obsahu.

4.  Pokud chcete zobrazit téma, zvolte ze seznamu výsledků její název.

## <a name="full-text-search-tips"></a>Tipy pro fulltextové vyhledávání

Můžete vytvořit více cílových hledání, které vracejí pouze témata, které vás zajímají, pokud budete rozumět tomu, jak ovlivňuje syntaxe dotazu. Syntaxe obsahuje speciální znaky, rezervovaná slova a filtry. Toto téma obsahuje tipy, postupy a podrobné informace o syntaxi můžete lepší plavidla své dotazy.

### <a name="general-guidelines"></a>Obecné pokyny

Následující tabulka uvádí některé základní pravidla a pokyny pro vývoj vyhledávací dotazy v nápovědě.

|Syntaxe|Popis|
|------------|-----------------|
|Rozlišování velkých a malých písmen|Vyhledávání nejsou malá a velká písmena. Vytvořte kritéria hledání pomocí velké nebo malé znaky. Například "OLE" a "ole" vrátí stejné výsledky.|
|Kombinace znaků|Nelze hledat pouze jednotlivé písmena (a-z) nebo čísla (0-9). Pokud se pokusíte vyhledávání pro určité vyhrazená slova, například "a", "od" a "s", budou ignorovány. Další informace najdete v tématu [slova ignorován v hledání](#stopwords) dál v tomto tématu.|
|Pořadí vyhodnocení|Vyhledávací dotazy jsou vyhodnocovány zleva doprava.|

### <a name="search-syntax"></a>Syntaxe vyhledávání

Pokud zadáte řetězec hledání, který obsahuje více slova, jako jsou "word1 word2," Tento řetězec je stejné, jako zadání "word1 word2 a", která vrací pouze témata, která obsahují všechny jednotlivých slov ve vyhledávacím řetězci.

> [!IMPORTANT]
> - Hledání frázi nejsou podporovány. Pokud zadáte více slov v hledaný řetězec, vrácený témata bude obsahovat všechny slova, která jste zadali, ale nemusí nutně prokázat přesný řetězec, který jste zadali.
> - Logické operátory slouží k určení vztah mezi slova v hledané fráze. Můžete zahrnout logických operátorů, například AND, OR, NOT a TÉMĚŘ, k dalšímu upřesněte hledání. Například pokud hledáte "deklarace TÉMĚŘ sjednocení", bude součástí výsledků vyhledávání témata obsahující slova "deklarace" a "union" více než pár slov vedle sebe navzájem. Další informace najdete v tématu [logické operátory ve vyhledávacích výrazech](../ide/logical-operators-in-search-expressions.md).

### <a name="filters"></a>Filtry

Pomocí rozšířeného vyhledávání operátorů lze dále omezit výsledky vyhledávání. Nápověda obsahuje tři kategorie, které můžete použít pro filtrování výsledků fulltextové vyhledávání: název, kód a – klíčové slovo.

### <a name="ranking-of-search-results"></a>Řazení výsledků vyhledávání

Vyhledávací algoritmus platí určitá kritéria, můžete pořadí výsledky vyšší nebo nižší v seznamu výsledků hledání. Obecně platí:

1.  Obsah, který zahrnuje hledaná slova v názvu je vyšší než obsah, který není seřazeny.

2.  Obsah, který obsahuje hledaná slova v těsné blízkosti je vyšší než obsah, který není seřazeny.

3.  Obsah, který obsahuje vyšší hustotu hledaná slova je vyšší než obsah, který má nižší hustotu hledaná slova seřazeny.

### <a name="stopwords"> Slova ignorovat ve vyhledávání (stop slov) </a>

Nejčastěji se vyskytující slova nebo čísel, které se někdy označují jako stop slov, jsou automaticky ignorovat během fulltextového vyhledávání. Například pokud hledání pro frázi "průchod prostřednictvím" zobrazí výsledky hledání témata obsahující slovo "průchodu" však není "až".

## <a name="see-also"></a>Viz také

- [Rozšířené a logické operátory](../ide/logical-operators-in-search-expressions.md)
- [Postupy: hledání témat v rejstříku](../ide/how-to-find-topics-in-the-index.md)
- [Postupy: hledání témat v obsahu](../ide/how-to-find-topics-in-the-table-of-contents.md)
- [Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)