---
title: Používání regulárních výrazů v sadě Visual Studio | Microsoft Docs
ms.custom: 03/26/2018
ms.technology: vs-ide-general
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
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cd7da9b9993f2a3ae2d1eb94cad18e99f5281fde
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="using-regular-expressions-in-visual-studio"></a>Používání regulárních výrazů v sadě Visual Studio

Visual Studio použije [regulární výrazy rozhraní .NET Framework](/dotnet/standard/base-types/regular-expressions) k vyhledání a nahrazení textu.

## <a name="replacement-patterns"></a>Vzory pro nahrazování

Chcete-li použít skupinu číslovaných zachycení, uzavřete skupiny v závorkách v regulární výraz. Použití `$number`, kde `number` je celé číslo od 1, zadat konkrétní, číslem skupiny vzorek pro nahrazení. Například seskupené regulární výraz `(\d)([a-z])` definuje dvě skupiny: první skupinu jednu číslici desítkové soustavy a druhé skupině obsahuje jeden znak mezi **a** a **z**. Výraz najde čtyři odpovídá v následující řetězec: **1a 2b 3c 4d**. Náhradní řetězec `z$1` odkazuje na první skupinu pouze a převede řetězec na **z1 z2 z3 z4**.

Informace o regulárních výrazech, které se používají v vzory pro nahrazování najdete v tématu [nahrazení v regulárních výrazech (Průvodce .NET)](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="regular-expression-examples"></a>Příklady regulárních výrazů

Následuje několik příkladů:

|Účel|Výraz|Příklad|
|-------------|----------------|-------------|
|Nahradit libovolný znak (s výjimkou konec řádku)|.|`a.o` odpovídá "aro" v "kolem" a "abo" v "o", ale ne "akro" v "mezi".|
|Porovná nula nebo více výskytů předcházejícího výrazu (porovnávat tolik znaků jako možné)|*|`a*r` odpovídá "r" v "rack", "ar" v "ark" a "aar" v "aardvark"|
|Porovná libovolný znak vícekrát nebo (zástupný znak *)|.*|c.*e odpovídá "cke" v "povyk", "comme" v "komentář" a "kód" v "kód"|
|Porovná jeden nebo více výskytů předcházejícího výrazu (porovnávat tolik znaků jako možné)|+|`e.+e` odpovídá "eede" v "podavač", ale ne "ee".|
|Porovná libovolný znak jeden nebo více dobu (zástupný znak?)|.+|e. + e odpovídá "eede" v "podavač", ale ne "ee".|
|Porovná nula nebo více výskytů předcházejícího výrazu (odpovídat jako několika prvních znaků nejdříve)|*?|`e.*?e` odpovídá "ee" v "podavač", ale ne "eede".|
|Porovná jeden nebo více výskytů předcházejícího výrazu (odpovídat jako několika prvních znaků nejdříve)|+?|`e.+?e` odpovídá "ente" a "erprise" v "enterprise", ale není celá slova "podniku".|
|Ukotvení shodu řetězce na začátek řádku nebo řetězce|^|`^car` slovo "auto" odpovídá pouze v případě, že se zobrazuje na začátku řádku.|
|Ukotvení shodu řetězce na konec řádku|\r?$|`End\r?$` odpovídá "end" pouze když zobrazí se na konci řádku.|
|Nahradit libovolný znak v sadě|[abc]|`b[abc]` odpovídá "ba", "bb" a "bc".|
|Porovná libovolný znak v rozsah znaků|[a-f]|`be[n-t]` odpovídá "tipu" v "mezi", "ben" v "pod" a "bes" v "vedle", ale ne "níže".|
|Zaznamenání a implicitně číslo výraz obsažené v závorky|()|`([a-z])X\1` odpovídá "aXa" a "bXb", ale ne "aXb". "\1" odkazuje na první skupinu výraz "[a-z]".|
|Zrušení platnosti shody|(?!abc)|`real (?!ity)` odpovídá "Skutečná" v "nemovitosti" a "skutečně", ale ne v "skutečností." Vyhledá také druhý "reálné" (ale ne první "skutečné") v "realityreal".|
|Porovná libovolný znak, který není v dané sadě znaků|[^abc]|`be[^n-t]` odpovídá "bef" v "před", "Bá" v "za" a "bel" v "níže", ale ne "pod".|
|Odpovídat výrazu před nebo po symbol jeden.|&#124;|`(sponge&#124;mud) bath` odpovídá "houba lázně" a "bláta lázeň."|
|Řídicí znak následující zpětné lomítko| \\ |`\^` odpovídá znak ^.|
|Zadejte počet výskytů předchozí znaku nebo skupiny|{x}, kde x je počet výskytů|`x(ab){2}x` odpovídá "xababx", a `x(ab){2,3}x` odpovídá "xababx" a "xabababx", ale ne "xababababx".|
|Porovná text ve třídě znaků Unicode, kde "X" je číslo kódování Unicode. Další informace o třídách znak Unicode najdete v tématu<br /><br /> [Vlastnosti znak Unicode Standard 5.2](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}` odpovídá "T" a "D" v "Thomas Doe".|
|Porovnat hranici slova|`\b` (Mimo třídu znaků \b Určuje hranici slova a uvnitř znak třída určuje backspace).|`\bin` odpovídá "v" v "uvnitř" však není "pinto".|
|Odpovídat konec řádku (to znamená, návrat na začátek následuje nového řádku).|\r?\n|`End\r?\nBegin` odpovídá "End" a "Begin", jenom když je poslední řetězec v řádku "End" a "Počáteční" je první řetězec v dalším řádku.|
|Porovná libovolný alfanumerický znak|\w|`a\wd` odpovídá "Přidat" a "a1d", ale ne "a d".|
|Porovná libovolný znak prázdný znak.|(?([^\r\n])\s)|`Public\sInterface` odpovídá frázi "Veřejné rozhraní".|
|Porovná libovolný znak číselné|\d|`\d` odpovídá a "3" v "3456", "2" v 23" a"1"v"1".|
|Porovná znak Unicode|\uXXXX kde XXXX Určuje hodnotu znak Unicode.|`\u0065` odpovídá znak "e".|
|Shodovat s identifikátorem|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|Odpovídá "type1", ale ne & type1 "nebo" #define ".|
|Porovnání řetězce v uvozovkách|((\\".+?\\")&#124;('.+?'))|Odpovídá jakémukoli řetězci v jednoduchých nebo dvojitých uvozovek.|
|Odpovídat o hexadecimální číslo|\b0[xX]([0-9a-fA-F]\)\b|Odpovídá "0xc67f", ale ne "0xc67fc67f".|
|Celá čísla shody a počet desetinných míst|\b[0-9]*\\.\*[0-9]+\b|Odpovídá "1,333".|

> [!TIP]
> V operačních systémech Windows většina řádky končit "\r\n" (návrat na začátek následuje nového řádku). Tyto znaky nejsou viditelná, ale jsou k dispozici v editoru a se předávají ke službě .NET regulární výraz.

## <a name="see-also"></a>Viz také

[Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)