---
title: Použít regulární výrazy
ms.date: 03/26/2018
ms.topic: conceptual
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c4e461fd69e048e406fbe062ff297da9baab3696
ms.sourcegitcommit: 8562a337cc9f674c756a4a0b2c7e288ebd61b51e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2019
ms.locfileid: "68345742"
---
# <a name="use-regular-expressions-in-visual-studio"></a>Použití regulárních výrazů v sadě Visual Studio

Visual Studio používá [regulární výrazy .NET](/dotnet/standard/base-types/regular-expressions) k hledání a nahrazování textu.

## <a name="regular-expression-examples"></a>Příklady regulárních výrazů

Následující tabulka obsahuje některé znaky regulárního výrazu, operátory, konstrukce a příklady vzorů. Podrobnější informace najdete v tématu [Jazyk regulárních výrazů](/dotnet/standard/base-types/regular-expression-language-quick-reference).

|Účel|Výraz|Příklad|
|-------------|----------------|-------------|
|Odpovídá jakémukoli jednomu znaku (s výjimkou konce řádku). Další informace naleznete v tématu [libovolný znak](/dotnet/standard/base-types/character-classes-in-regular-expressions#any-character-).|.|`a.o` odpovídá "ARO" ve slově "around" a "abo" ve "o" ale ne "acro" v "v".|
|Porovná žádný nebo více výskytů předcházejícího výrazu (odpovídá tolik znakům, kolik jich je možné). Další informace naleznete v tématu [neshoda nula nebo](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-)vícekrát.|*|`a*r` odpovídá "r" ve "rack", "ar" ve slově "ark" a "aar" ve slově "aardvark"|
|Odpovídá jakémukoli znaku nula nebo vícekrát (zástupný znak \*)|.*|`c.*e` odpovídá "cke" ve "racket", "comme" ve "komentář" a "code" ve "kód"|
|Porovnává s jedním nebo více výskyty předcházejícího výrazu (odpovídá co nejvíce znakům). Další informace naleznete v tématu [porovnává jednou nebo](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-)vícekrát.|+|`e.+d` odpovídá "rychlost" ve "slově feeder" ale ne "upravit".|
|Odpovídá jakémukoli znaku jednou nebo vícekrát (zástupný znak?)|.+|`e.+e` odpovídá "eede" ve "slově feeder" ale ne "ee".|
|Porovná žádný nebo více výskytů předcházejícího výrazu (odpovídá co nejvíce znakům). Další informace najdete v tématu [Shoda nula nebo vícekrát (opožděné porovnávání)](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-lazy-match-).|*?|`e.*?e` odpovídá "ee" ve "slově feeder" ale ne "eede".|
|Odpovídá jednomu nebo více výskytům předcházejícího výrazu (odpovídá co nejvíce znakům). Další informace najdete v tématu [vyhledání jedné nebo více časů (opožděné porovnávání)](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-lazy-match-).|+?|`e.+?e` odpovídá "ente" a "erprise" ve slově "enterprise", ale ne celému slovu "enterprise".|
|Ukotvení řetězce shody na [začátek řádku nebo řetězce](/dotnet/standard/base-types/anchors-in-regular-expressions#start-of-string-or-line-)|^|`^car` odpovídá slovu "car" pouze, pokud se nachází na začátku řádku.|
|Ukotvení řetězce shody na [konec řádku](/dotnet/standard/base-types/anchors-in-regular-expressions#end-of-string-or-line-)|\r?$|`end\r?$` odpovídá "end" pouze pokud je zobrazeno na konci řádku.|
|Ukotvení řetězce shody na konec souboru|$|`end$` odpovídá "end" pouze pokud je zobrazeno na konci souboru.|
|Odpovídá jakémukoli jednomu znaku v sadě|[abc]|`b[abc]` odpovídá "ba", "bb" a "bc".|
|Odpovídá jakémukoli znaku v rozsahu znaků|[a-f]|`be[n-t]` odpovídá "bet" v "between", "ben" v "beneath" a "bes" ve "beside", ale ne "below".|
|Zachytí a implicitně očísluje výraz v závorkách|()|`([a-z])X\1` porovnává "s aXa" a "bXb", ale nikoli "aXb". "\1" se vztahuje k první skupině výrazů "[a-z]". Další informace najdete v tématu [skupiny zachycení a vzory nahrazení](#capture-groups-and-replacement-patterns). |
|Znehodnotit shodu|(?! ABC)|`real(?!ity)` odpovídá "real" ve slově "realty" a "really", ale ne "reality." Najde také druhý "real" (ale ne první "real") v "realityreal".|
|Odpovídá jakémukoli znaku, který není v dané sadě znaků. Další informace naleznete v tématu [Skupina negativních znaků](/dotnet/standard/base-types/character-classes-in-regular-expressions#negative-character-group-).|[^ abc]|`be[^n-t]` odpovídá "bef" v "before", "beh" v "behind" a "bel" ve "below", ale ne "beneath".|
|Porovnává buď výraz před, nebo za symbolem.|&#124;|`(sponge\|mud) bath` odpovídá "výrazům relaxační koupel" a "bahenní koupel".|
|[Řídicí znak](/dotnet/standard/base-types/character-escapes-in-regular-expressions) za zpětným lomítkem| \\ |`\^` odpovídá znaku ^.|
|Zadejte počet výskytů předcházejícího znaku nebo skupiny. Další informace najdete v tématu [vyhledání přesně n krát](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-exactly-n-times-n).|{n}, kde n je počet výskytů|`x(ab){2}x` odpovídá "xababx" a `x(ab){2,3}x` odpovídá "xababx" a "xabababx" ale ne "xababababx".|
|[Odpovídá textu v kategorii Unicode](/dotnet/standard/base-types/character-classes-in-regular-expressions#unicode-category-or-unicode-block-p). Další informace o třídách znaků Unicode naleznete v tématu [vlastnosti znaků Unicode Standard 5,2](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}, kde "X" je číslo sady Unicode.|`\p{Lu}` odpovídá "T" a "D" v "Thomas Doe".|
|[Odpovídá hranici slova](/dotnet/standard/base-types/anchors-in-regular-expressions#word-boundary-b)|\b (mimo třídu znaků `\b` určuje hranici slova a uvnitř třídy znaků `\b` Určuje znak backspace.)|`\bin` odpovídá "in" v "inside" ale ne "pinto".|
|Odpovídá zalomení řádku (tj. znak návratu na začátek řádku následovaný novým řádkem).|\r?\n|`End\r?\nBegin` odpovídá "End" a "Begin" pouze, když je "End" posledním řetězcem v řádku a "Begin" je první řetězec v následujícím řádku.|
|Odpovídá jakémukoli [znaku slova](/dotnet/standard/base-types/character-classes-in-regular-expressions#word-character-w)|\w|`a\wd` odpovídá "Přidat" a "a1d", ale ne "a d".|
|Odpovídá jakémukoli [prázdnému znaku](/dotnet/standard/base-types/character-classes-in-regular-expressions#whitespace-character-s)|\s|`Public\sInterface` odpovídá slovnímu "Veřejné rozhraní".|
|Odpovídá libovolnému [znaku desítkové číslice](/dotnet/standard/base-types/character-classes-in-regular-expressions#decimal-digit-character-d)|\d|`\d` shody a "3" v "3456", "2" ve "23" a "1" v "1".|
|Odpovídá znaku Unicode|\uXXXX kde XXXX Určuje hodnotu znaku Unicode.|`\u0065` odpovídá znaku "e".|
|Odpovídá identifikátoru|\b [\_\w-[0-9]] [\_\w]*\b|Odpovídá "type1" ale ne "& type1" nebo "#define".|
|Odpovídá řetězci v uvozovkách|((\\".+?\\")&#124;('.+?'))|Odpovídá jakémukoli řetězci v jednoduchých nebo dvojitých uvozovkách.|
|Shoda s šestnáctkovým číslem|\b0[xX]([0-9a-fA-F]+\)\b|Porovná "0xc67f", ale ne "0xc67g".|
|Odpovídá celým nebo desetinným a desetinných míst|\b[0-9]*\\.\*[0-9]+\b|Odpovídá "1,333".|

> [!TIP]
> V operačních systémech Windows většina řádků končí "\r\n" (zalomení řádku a nový řádek). Tyto znaky nejsou viditelné, ale jsou k dispozici v editoru a jsou předány službě regulárních výrazů .NET.

## <a name="capture-groups-and-replacement-patterns"></a>Skupiny zachycení a vzory nahrazení

Skupina zachycení vymezují dílčí výraz regulárního výrazu a zachycuje podřetězec vstupního řetězce. Můžete použít zachycené skupiny v rámci samotného regulárního výrazu (například pro hledání opakovaného slova) nebo ve vzoru pro nahrazení. Podrobné informace naleznete v tématu [seskupovací konstrukce v regulárních výrazech](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).

Chcete-li vytvořit číslovanou skupinu zachycení, uzavřete dílčí výraz se závorkami ve vzoru regulárního výrazu. Zachycení jsou očíslována automaticky zprava doleva na základě pozice levé závorky v regulárním výrazu. Přístup k zachycené skupině:

- **v rámci regulárního výrazu**: Použijte `\number`. Například `\1` v regulárním výrazu `(\w+)\s\1` odkazuje na první skupinu `(\w+)`zachycení.

- **ve vzoru pro nahrazení**: Použijte `$number`. Například seskupené regulární výraz `(\d)([a-z])` definuje dvě skupiny: první skupinu jednu číslici desítkové soustavy a druhé skupině obsahuje jeden znak mezi **a** a **z**. Výraz najde čtyři shody v následujícím řetězci: **1a 2b 3c 4d**. Řetězec `z$1` pro nahrazení odkazuje pouze na první skupinu (`$1`) a převede řetězec na **Z1 Z2 Z3 Z4**.

Následující obrázek ukazuje regulární výraz `(\w+)\s\1` a náhradní řetězec. `$1` Regulární výraz i vzor pro nahrazení odkazují na první skupinu zachycení, která je automaticky očíslována 1. Zvolíte-li možnost **Nahradit vše** v dialogovém okně **rychlé nahrazení** v aplikaci Visual Studio, jsou z textu odstraněna opakující se slova.

![Rychlé nahrazení znázorňující očíslovanou skupinu zachycení v aplikaci Visual Studio](media/numbered-capture-group.png)

> [!TIP]
> Ujistěte se, že je v dialogovém okně **rychlé nahrazení** vybráno tlačítko **použít regulární výrazy** .

### <a name="named-capture-groups"></a>Pojmenované skupiny zachycení

Místo toho, abyste se museli spoléhat na automatické číslování skupiny zachycení, můžete mu dát název. Syntaxe pojmenované skupiny zachycení je `(?<name>subexpression)`.

Pojmenované skupiny zachycení, jako jsou číslované skupiny zachycení, lze použít v rámci samotného regulárního výrazu nebo ve vzoru pro nahrazení. Přístup k pojmenované skupině zachycení:

- **v rámci regulárního výrazu**: Použijte `\k<name>`. Například `\k<repeated>` v regulárním výrazu `(?<repeated>\w+)\s\k<repeated>` odkazuje na skupinu zachycení s názvem `repeated` a jejíž dílčí výraz je `\w+`.

- **ve vzoru pro nahrazení**: Použijte `${name}`. Například, `${repeated}`.

Jako příklad ukazuje následující obrázek regulární výraz `(?<repeated>\w+)\s\k<repeated>` a náhradní řetězec. `${repeated}` Regulární výraz i vzor pro nahrazení odkazují na skupinu zachycení s názvem `repeated`. Zvolíte-li možnost **Nahradit vše** v dialogovém okně **rychlé nahrazení** v aplikaci Visual Studio, jsou z textu odstraněna opakující se slova.

![Rychlé nahrazení zobrazující pojmenovanou skupinu zachycení v aplikaci Visual Studio](media/named-capture-group.png)

> [!TIP]
> Ujistěte se, že je v dialogovém okně **rychlé nahrazení** vybráno tlačítko **použít regulární výrazy** .

Další informace o pojmenovaných skupinách zachycení naleznete v tématu [pojmenované odpovídající](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions#named-matched-subexpressions)podvýrazy. Další informace o regulárních výrazech, které jsou použity v vzorech pro nahrazení, naleznete v tématu [substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="see-also"></a>Viz také:

- [Jazyk regulárních výrazů](/dotnet/standard/base-types/regular-expression-language-quick-reference)
- [Vyhledání a nahrazení textu](../ide/finding-and-replacing-text.md)
