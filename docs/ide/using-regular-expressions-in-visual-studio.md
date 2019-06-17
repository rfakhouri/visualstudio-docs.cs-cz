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
ms.openlocfilehash: b20cf3692cf76f602eb11b0a53a1669c919f1679
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043573"
---
# <a name="use-regular-expressions-in-visual-studio"></a>Použití regulárních výrazů v sadě Visual Studio

Visual Studio používá [regulárních výrazů .NET](/dotnet/standard/base-types/regular-expressions) najít a nahradit text.

## <a name="regular-expression-examples"></a>Příklady regulárních výrazů

Následující tabulka obsahuje některé znaky regulárního výrazu, operátory, konstruktory a příklady vzor. Odkaz na kompletní, naleznete v tématu [jazyk regulárních výrazů](/dotnet/standard/base-types/regular-expression-language-quick-reference).

|Účel|Výraz|Příklad|
|-------------|----------------|-------------|
|Odpovídá jakémukoli jednomu znaku (s výjimkou konce řádku). Další informace najdete v tématu [libovolný znak](/dotnet/standard/base-types/character-classes-in-regular-expressions#any-character-).|.|`a.o` odpovídá "ARO" ve slově "around" a "abo" ve "o" ale ne "acro" v "v".|
|Odpovídá žádnému nebo více výskytům předcházejícího výrazu (odpovídá co nejvíce znakům). Další informace najdete v tématu [odpovídat nulakrát nebo vícekrát](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-).|*|`a*r` odpovídá "r" ve "rack", "ar" ve slově "ark" a "aar" ve slově "aardvark"|
|Odpovídá jakémukoli znaku nula nebo vícekrát (zástupný znak \*)|.*|`c.*e` odpovídá "cke" ve "racket", "comme" ve "komentář" a "code" ve "kód"|
|Odpovídá jeden nebo více výskytům předcházejícího výrazu (odpovídá co nejvíce znakům). Další informace najdete v tématu [shodovat s jednou nebo vícekrát](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-).|+|`e.+d` odpovídá "rychlost" ve "slově feeder" ale ne "upravit".|
|Odpovídá jakémukoli znaku jednou nebo vícekrát (zástupný znak?)|.+|`e.+e` odpovídá "eede" ve "slově feeder" ale ne "ee".|
|Odpovídá žádnému nebo více výskytům předcházejícího výrazu (odpovídá co nejméně znakům). Další informace najdete v tématu [odpovídat nula nebo vícekrát (opožděné shoda)](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-zero-or-more-times-lazy-match-).|*?|`e.*?e` odpovídá "ee" ve "slově feeder" ale ne "eede".|
|Odpovídá jeden nebo více výskytům předcházejícího výrazu (odpovídá co nejméně znakům). Další informace najdete v tématu [shodovat s jednou nebo vícekrát (opožděné shoda)](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-one-or-more-times-lazy-match-).|+?|`e.+?e` odpovídá "ente" a "erprise" ve slově "enterprise", ale ne celému slovu "enterprise".|
|Ukotvení řetězce shody na [začátek řetězce nebo řádku](/dotnet/standard/base-types/anchors-in-regular-expressions#start-of-string-or-line-)|^|`^car` odpovídá slovu "car" pouze, pokud se nachází na začátku řádku.|
|Ukotvení řetězce shody na [konec řádku](/dotnet/standard/base-types/anchors-in-regular-expressions#end-of-string-or-line-)|\r?$|`end\r?$` odpovídá "end" pouze pokud je zobrazeno na konci řádku.|
|Ukotvení řetězce shody na konec souboru|$|`end$` odpovídá "end" pouze pokud je zobrazeno na konci souboru.|
|Odpovídá jakémukoli jednomu znaku v sadě|[abc]|`b[abc]` odpovídá "ba", "bb" a "bc".|
|Odpovídá jakémukoli znaku v rozsahu znaků|[a-f]|`be[n-t]` odpovídá "bet" v "between", "ben" v "beneath" a "bes" ve "beside", ale ne "below".|
|Zachytí a implicitně očísluje výraz v závorkách|()|`([a-z])X\1` porovnává "s aXa" a "bXb", ale nikoli "aXb". "\1" se vztahuje k první skupině výrazů "[a-z]".|
|Znehodnotit shodu|(?! ABC)|`real(?!ity)` odpovídá "real" ve slově "realty" a "really", ale ne "reality." Najde také druhý "real" (ale ne první "real") v "realityreal".|
|Odpovídá jakémukoli znaku, který není v dané sadě znaků. Další informace najdete v tématu [Skupina negativních znaků](/dotnet/standard/base-types/character-classes-in-regular-expressions#negative-character-group-).|[^ abc]|`be[^n-t]` odpovídá "bef" v "before", "beh" v "behind" a "bel" ve "below", ale ne "beneath".|
|Odpovídá výrazu před nebo jednomu za symbolem|&#124;|`(sponge\|mud) bath` odpovídá "výrazům relaxační koupel" a "bahenní koupel".|
|[Řídicí sekvence pro znak](/dotnet/standard/base-types/character-escapes-in-regular-expressions) po zpětném lomítku| \\ |`\^` odpovídá znaku ^.|
|Zadejte počet výskytů předchozího znaku nebo skupiny. Další informace najdete v tématu [odpovídá přesně n vícekrát](/dotnet/standard/base-types/quantifiers-in-regular-expressions#match-exactly-n-times-n).|{n}, kde n je počet výskytů|`x(ab){2}x` odpovídá "xababx" a `x(ab){2,3}x` odpovídá "xababx" a "xabababx" ale ne "xababababx".|
|[Porovnání textu několika kategorie sady Unicode](/dotnet/standard/base-types/character-classes-in-regular-expressions#unicode-category-or-unicode-block-p). Další informace o třídách znaků Unicode naleznete v tématu [Unicode Standard 5.2 znak vlastnosti](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}, kde "X" je číslo sady Unicode.|`\p{Lu}` odpovídá "T" a "D" v "Thomas Doe".|
|[Porovná hranici slova](/dotnet/standard/base-types/anchors-in-regular-expressions#word-boundary-b)|\b (mimo třídu znaků `\b` určuje hranici slova a uvnitř třídy znaků `\b` Určuje znak backspace.)|`\bin` odpovídá "in" v "inside" ale ne "pinto".|
|Odpovídá konci řádku (to znamená zalomení řádku a nový řádek)|\r?\n|`End\r?\nBegin` odpovídá "End" a "Begin" pouze, když je "End" posledním řetězcem v řádku a "Begin" je první řetězec v následujícím řádku.|
|Shodují s některým [znak slova](/dotnet/standard/base-types/character-classes-in-regular-expressions#word-character-w)|\w|`a\wd` odpovídá "Přidat" a "a1d", ale ne "a d".|
|Shodují s některým [prázdnému znaku](/dotnet/standard/base-types/character-classes-in-regular-expressions#whitespace-character-s)|\s|`Public\sInterface` odpovídá slovnímu "Veřejné rozhraní".|
|Shodují s některým [znak desítkové číslice](/dotnet/standard/base-types/character-classes-in-regular-expressions#decimal-digit-character-d)|\d|`\d` shody a "3" v "3456", "2" ve "23" a "1" v "1".|
|Odpovídá znaku Unicode|\uXXXX kde XXXX Určuje hodnotu znaku Unicode.|`\u0065` odpovídá znaku "e".|
|Odpovídá identifikátoru|\b [\_\w-[0-9]] [\_\w]*\b|Odpovídá "type1" ale ne "& type1" nebo "#define".|
|Odpovídá řetězci v uvozovkách|((\\".+?\\")&#124;('.+?'))|Odpovídá jakémukoli řetězci v jednoduchých nebo dvojitých uvozovkách.|
|Shoda s šestnáctkovým číslem|\b0[xX]([0-9a-fA-F]+\)\b|Odpovídá "0xc67f" ale ne "0xc67g".|
|Odpovídá celým nebo desetinným a desetinných míst|\b[0-9]*\\.\*[0-9]+\b|Odpovídá "1,333".|

> [!TIP]
> V operačních systémech Windows většina řádků končí "\r\n" (zalomení řádku a nový řádek). Tyto znaky nejsou viditelné, ale jsou k dispozici v editoru a jsou předány službě regulárních výrazů .NET.

## <a name="capture-groups-and-replacement-patterns"></a>Skupin zachycení a vzory pro nahrazení

Skupina zachycení kolem dílčí výraz regulárního výrazu a zachytí podřetězce vstupního řetězce. Můžete použít zachycené skupiny v rámci regulárního výrazu, samotný (například hledat opakované word), nebo ve vzorech pro nahrazení. Podrobné informace najdete v tématu [seskupovací konstrukce v regulárních výrazech](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).

Pokud chcete vytvořit číslovanou zachycenou skupinu, před a za dílčí výraz pomocí závorek ve vzorku regulárního výrazu. Zachycení jsou automaticky číslovány zleva doprava na základě pozice levou závorku v regulárním výrazu. Pro přístup k zachycené skupiny:

- **v rámci regulárního výrazu**: Použití `\number`. Například `\1` v regulárním výrazu `(\w+)\s\1` odkazuje na první skupiny zachycení `(\w+)`.

- **ve vzorech pro nahrazení**: Použití `$number`. Například seskupené regulární výraz `(\d)([a-z])` definuje dvě skupiny: první skupinu jednu číslici desítkové soustavy a druhé skupině obsahuje jeden znak mezi **a** a **z**. Výraz najde čtyři shod v následující řetězec: **1a 2b 3c 4d**. Řetězci pro nahrazení `z$1` odkazuje pouze první skupina (`$1`) a převede řetězec na **z1 z2 z3 z4**.

Následující obrázek ukazuje regulární výraz `(\w+)\s\1` a řetězci pro nahrazení `$1`. Vzor regulárního výrazu a vzor pro nahrazení odkazovat na první skupině zachycení, který se má automaticky číslované 1. Pokud zvolíte **Nahradit vše** v **rychlého nahrazení** dialogové okno v sadě Visual Studio opakovaná slova jsou odebrány z textu.

![Rychlé nahrazení zobrazující číslovanou zachycenou skupinu v sadě Visual Studio](media/numbered-capture-group.png)

> [!TIP]
> Ujistěte se, že **pomocí regulárních výrazů** ve výběru tlačítka **rychlého nahrazení** dialogové okno.

### <a name="named-capture-groups"></a>Zachycení pojmenované skupiny

Aniž byste museli spoléhat na automatické číslování skupině zachycení, můžete jí název. Syntaxe pro skupinu s názvem zachycení je `(?<name>subexpression)`.

Pojmenované skupiny zachycení, jako jsou číslované skupiny zachycení, je možné v rámci samotného regulárního výrazu nebo ve vzorech pro nahrazení. Pro přístup ke skupině pojmenované zachycení:

- **v rámci regulárního výrazu**: Použití `\k<name>`. Například `\k<repeated>` v regulárním výrazu `(?<repeated>\w+)\s\k<repeated>` odkazuje skupina zachycení, který je pojmenován `repeated` a jejichž dílčí výraz `\w+`.

- **ve vzorech pro nahrazení**: Použití `${name}`. Například, `${repeated}`.

Například následující obrázek ukazuje regulární výraz `(?<repeated>\w+)\s\k<repeated>` a řetězci pro nahrazení `${repeated}`. Vzor regulárního výrazu a vzor pro nahrazení odkazovat zachycení skupina s názvem `repeated`. Pokud zvolíte **Nahradit vše** v **rychlého nahrazení** dialogové okno v sadě Visual Studio opakovaná slova jsou odebrány z textu.

![Rychlé nahrazení zobrazuje skupina s názvem zachycení v sadě Visual Studio](media/named-capture-group.png)

> [!TIP]
> Ujistěte se, že **pomocí regulárních výrazů** ve výběru tlačítka **rychlého nahrazení** dialogové okno.

Další informace o skupinách pojmenované zachycení, naleznete v tématu [pojmenované odpovídající podvýrazy](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions#named-matched-subexpressions). Další informace o formátování regulárních výrazů, které se používají ve vzorech pro nahrazení najdete v tématu [nahrazení v regulárních výrazech](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="see-also"></a>Viz také:

- [Jazyk regulárních výrazů](/dotnet/standard/base-types/regular-expression-language-quick-reference)
- [Vyhledání a nahrazení textu](../ide/finding-and-replacing-text.md)
