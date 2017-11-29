---
title: "Používání regulárních výrazů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
- Visual Studio, regular expressions
ms.assetid: 718a617d-0e05-47e1-a218-9746971527f4
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c01023649879c34838cbca3172aec6b5a053f4bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-regular-expressions-in-visual-studio"></a>Používání regulárních výrazů v sadě Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]regulární výrazy rozhraní .NET Framework se používá k vyhledání a nahrazení textu. Další informace o regulárních výrazech .NET najdete v tématu [regulární výrazy rozhraní .NET Framework](/dotnet/standard/base-types/regular-expressions).  
  
 Před sady Visual Studio 2012 sadě Visual Studio použít vlastní regulární výraz syntaxe v systému windows najít a nahradit. V tématu [Visual Studio regulární výraz převody](https://msdn.microsoft.com/en-us/library/2k3te2cs\(v=vs.110\).aspx) Další informace o tom, jak převést některé symbolů informace použití vlastní regulární výraz na verze rozhraní .NET.  
  
> [!TIP]
>  V operačních systémech Windows většina řádky končit "\r\n" (návrat na začátek následuje nového řádku). Tyto znaky se nezobrazí, ale jsou k dispozici v editoru a jsou předávány službu regulární výraz platformy .NET.  
  
> [!TIP]
>  Informace o regulárních výrazech, které se používají v vzory pro nahrazování najdete v tématu [náhrady](/dotnet/standard/base-types/substitutions-in-regular-expressions). Chcete-li použít skupinu číslovaných zachycení, syntaxe je `$1` k určení číslem skupiny a `(x)` k určení dané skupiny. Například seskupené regulární výraz `(\d)([a-z])` najde čtyři odpovídá v následující řetězec: **1a 2b 3c 4d**. Náhradní řetězec `z$1` převede tento řetězec k **z1 z2 z3 z4**.  
  
## <a name="regular-expressions-in-visual-studio"></a>Regulární výrazy v sadě Visual Studio  
 Zde jsou některé příklady  
  
|Účel|Výraz|Příklad|  
|-------------|----------------|-------------|  
|Nahradit libovolný znak (s výjimkou konec řádku)|.|`a.o`odpovídá "aro" v "kolem" a "abo" v "o", ale ne "akro" v "mezi".|  
|Porovná nula nebo více výskytů předcházejícího výrazu (porovnávat tolik znaků jako možné)|*|`a*r`odpovídá "r" v "rack", "ar" v "ark" a "aar" v "aardvark"|  
|Porovná libovolný znak vícekrát nebo (zástupný znak *)|.*|c.*e odpovídá "cke" v "povyk", "comme" v "komentář" a "kód" v "kód"|  
|Porovná jeden nebo více výskytů předcházejícího výrazu (porovnávat tolik znaků jako možné)|+|`e.+e`odpovídá "eede" v "podavač", ale ne "ee".|  
|Porovná libovolný znak jeden nebo více dobu (zástupný znak?)|.+|e. + e odpovídá "eede" v "podavač", ale ne "ee".|  
|Porovná nula nebo více výskytů předcházejícího výrazu (odpovídat jako několika prvních znaků nejdříve)|*?|`e.*?e`odpovídá "ee" v "podavač", ale ne "eede".|  
|Porovná jeden nebo více výskytů předcházejícího výrazu (odpovídat jako několika prvních znaků nejdříve)|+?|`e.+?e`odpovídá "ente" a "erprise" v "enterprise", ale není celá slova "podniku".|  
|Ukotvení shodu řetězce na začátek řádku nebo řetězce|^|`^car`slovo "auto" odpovídá pouze v případě, že se zobrazuje na začátku řádku.|  
|Ukotvení shodu řetězce na konec řádku|\r?$|`End\r?$`odpovídá "end" pouze když zobrazí se na konci řádku.|  
|Nahradit libovolný znak v sadě|[abc]|`b[abc]`odpovídá "ba", "bb" a "bc".|  
|Porovná libovolný znak v rozsah znaků|[-f]|`be[n-t]`odpovídá "tipu" v "mezi", "ben" v "pod" a "bes" v "vedle", ale ne "níže".|  
|Zaznamenání a implicitně číslo výraz obsažené v závorky|()|`([a-z])X\1`odpovídá "aXa" a "bXb", ale ne "aXb". ". "\1" odkazuje na první skupinu výraz "[a-z]".|  
|Zrušení platnosti shody|(?! ABC)|`real (?!ity)`odpovídá "Skutečná" v "nemovitosti" a "skutečně", ale ne v "skutečností." Vyhledá také druhý "reálné" (ale ne první "skutečné") v "realityreal".|  
|Porovná libovolný znak, který není v dané sadě znaků|[^ abc]|`be[^n-t]`odpovídá "bef" v "před", "Bá" v "za" a "bel" v "níže", ale ne "pod".|  
|Odpovídat výrazu před nebo po symbol jeden.|&#124;|`(sponge&#124;mud) bath`odpovídá "houba lázně" a "bláta lázeň."|  
|Řídicí znak následující zpětné lomítko|\|`\^`odpovídá znak ^.|  
|Zadejte počet výskytů předchozí znaku nebo skupiny|{x}, kde x je počet výskytů|`x(ab){2}x`odpovídá "xababx", a `x(ab){2,3}x` odpovídá "xababx" a "xabababx", ale ne "xababababx".|  
|Porovná text ve třídě znaků Unicode, kde "X" je číslo kódování Unicode. Další informace o třídách znak Unicode najdete v tématu<br /><br /> [Vlastnosti znak Unicode Standard 5.2](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}`odpovídá "T" a "D" v "Thomas Doe".|  
|Porovnat hranici slova|`\b`(Mimo třídu znaků \b Určuje hranici slova a uvnitř znak třída určuje backspace).|`\bin`odpovídá "v" v "uvnitř" však není "pinto".|  
|Odpovídat konec řádku (ie návrat na začátek následuje nového řádku).|\r?\n|`End\r?\nBegin`odpovídá "End" a "Begin", jenom když je poslední řetězec v řádku "End" a "Počáteční" je první řetězec v dalším řádku.|  
|Porovná libovolný alfanumerický znak|\w|`a\wd`odpovídá "Přidat" a "a1d", ale ne "a d".|  
|Porovná libovolný znak prázdný znak.|(? ([^ \r\n])\s)|`Public\sInterface`odpovídá frázi "Veřejné rozhraní".|  
|Porovná libovolný znak číselné|\d|`\d`odpovídá a "3" v "3456", "2" v 23" a"1"v"1".|  
|Porovná znak Unicode|\uXXXX kde XXXX Určuje hodnotu znak Unicode.|`\u0065`odpovídá znak "e".|  
|Shodovat s identifikátorem|\b (_\w + &#124; [\w-[0-9\_]] \w*)\b|Odpovídá "type1", ale ne & type1 "nebo" #define ".|  
|Porovnání řetězce v uvozovkách|((\\".+?\\")&#124;('.+?'))|Odpovídá jakémukoli řetězci v jednoduchých nebo dvojitých uvozovek.|  
|Odpovídat o hexadecimální číslo|\b0[xX]([0-9a-fA-F]\)\b|Odpovídá "0xc67f", ale ne "0xc67fc67f".|  
|Celá čísla shody a počet desetinných míst|\b[0-9]*\\.\* [0-9] + \b|Odpovídá "1,333".|  
  
## <a name="see-also"></a>Viz také  
 [Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)