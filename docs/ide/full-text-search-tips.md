---
redirect_url: /visualstudio/ide/how-to-search-for-topics
ms.openlocfilehash: a66c168ca81b22c32fc05afddd01266950791d1e
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
Title: "tipy pro fulltextové vyhledávání | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 11/04/2016":" "ms.suite:" "ms.technology: 
  - ms.tgt_pltfrm "vs Prohlížeč nápovědy": "" ms.topic: "článku" f1_keywords: 
  - helpviewer_keywords "hv_search": 
  - "Help Viewer, tipy pro fulltextové vyhledávání"
  - "tipy fulltextové vyhledávání [Help Viewer]" ms.assetid: bcaad23d-2ca7-4bec-8b54-b884bc34e70b caps.latest.revision: 13 Autor: ms.author "gewarren": "gewarren" správce: ghogen
---
# <a name="full-text-search-tips"></a>Tipy pro fulltextové vyhledávání
Jedním z užitečnější metod vyhledávání informací v nápovědě, je provádění fulltextové vyhledávání. Můžete vytvořit více cílových hledání, které vracejí pouze témata, které vás zajímají, pokud budete rozumět tomu, jak ovlivňuje syntaxe dotazu. Syntaxe obsahuje speciální znaky, rezervovaná slova a filtry. Toto téma obsahuje tipy, postupy a podrobné informace o syntaxi můžete lepší plavidla své dotazy.
  
### <a name="general-guidelines"></a>Obecné pokyny  
Následující tabulka uvádí některé základní pravidla a pokyny pro vývoj vyhledávací dotazy v nápovědě.  
  
|Syntaxe|Popis|  
|------------|-----------------|  
|Rozlišování velkých a malých písmen|Vyhledávání nejsou malá a velká písmena. Vytvořte kritéria hledání pomocí velké nebo malé znaky. Například "OLE" a "ole" vrátí stejné výsledky.|  
|Kombinace znaků|Nelze hledat pouze jednotlivé písmena (a-z) nebo čísla (0-9). Pokud se pokusíte vyhledávání pro určité vyhrazená slova, například "a", "od" a "s", budou ignorovány. Další informace najdete v tématu "Slova ignorovaná ve vyhledávání (Stop slov)" dál v tomto tématu.|  
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
  
### <a name="words-ignored-in-searches-stop-words"></a>Slova ignorovat ve vyhledávání (stop slov)  
 Nejčastěji se vyskytující slova nebo čísel, které se někdy označují jako stop slov, jsou automaticky ignorovat během fulltextového vyhledávání. Například pokud hledání pro frázi "průchod prostřednictvím" zobrazí výsledky hledání témata obsahující slovo "průchodu" však není "až".  
  
## <a name="see-also"></a>Viz také
[Vyhledejte informace](../ide/locate-information.md)   
[Logické operátory ve vyhledávacích výrazech](../ide/logical-operators-in-search-expressions.md)