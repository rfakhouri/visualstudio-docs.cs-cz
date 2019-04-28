---
title: Vnitřní funkce
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _String_length_
- _Param_
- _Curr_
- _Old_
- _Nullterm_length_
- _Inexpressible_
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 41ac8e38f501152d329e788572c500f68a8d2214
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62820717"
---
# <a name="intrinsic-functions"></a>Vnitřní funkce
Výraz v SAL může být výraz jazyka C/C++, za předpokladu, že je výraz, který nemá žádné vedlejší účinky, například ++,--a všechny vedlejší účinky mají v tomto kontextu volání funkce.  Poznámky SAL však poskytuje některé funkce jako objekty a některé rezervované symboly, které můžete použít ve výrazech SAL. Tyto jsou označovány jako *vnitřní funkce*.

## <a name="general-purpose"></a>Obecné použití
 Následující poznámky instrinsic funkce poskytují obecné nástroje pro poznámky SAL.

|Poznámka|Popis|
|----------------|-----------------|
|`_Curr_`|Synonymum pro objekt, který je aktuálně poznámkou.  Když `_At_` poznámky se používá, `_Curr_` je stejný jako první parametr `_At_`.  V opačném případě je parametr nebo celé funkce/návratová hodnota, ke kterému je poznámka lexikálně přidružena.|
|`_Inexpressible_(expr)`|Vyjadřuje situaci, kde velikost vyrovnávací paměti je příliš složité pomocí výrazu anotace – například když je vypočítán prohledáním vstupní datové sady a potom počítání Vybraní členové.|
|`_Nullterm_length_(param)`|`param` je počet elementů ve vyrovnávací paměti až, ale nezahrnuje ukončovací znak null. Lze ji použít na všechny vyrovnávací paměti typu neagregované, jiný než void.|
|`_Old_(expr)`|Když je vyhodnocen v předběžné podmínce, `_Old_` vrátí vstupní hodnoty `expr`.  Když je vyhodnocen v po podmínka, vrátí hodnotu `expr` jako jeho by se vyhodnotily v předběžné podmínce.|
|`_Param_(n)`|`n`Th parametr funkce, počítáno od 1 do `n`, a `n` je literál integrální konstanta. Pokud je parametr pojmenovaný, tato poznámka se shoduje s přístupem k parametru podle názvu. **Poznámka:** `n` mohou odkazovat na poziční parametry, které jsou definovány pomocí tři teček nebo mohou být použity v prototypech funkcí nejsou-li použity názvy.|
|`return`|Vyhrazené klíčové slovo jazyka C/C++ `return` lze použít ve výrazu poznámky SAL k označení návratovou hodnotu funkce.  Hodnota je k dispozici pouze ve stavu příspěvku; Jedná se chybu syntaxe jeho použití v předem stavu.|

## <a name="string-specific"></a>Konkrétní řetězec
 Následující poznámky pro vnitřní funkce povolit manipulaci s řetězci. Všechny čtyři z těchto funkcí slouží stejnému účelu: k vrácení počtu prvků typu, který se nachází před ukončovací znak null. Rozdíly jsou typy dat v prvky, které jsou uvedené. Všimněte si, že pokud chcete zadat délku zakončený hodnotou null vyrovnávací paměti, který není tvořený znaky, použijte `_Nullterm_length_(param)` poznámky z předchozí části.

|Poznámka|Popis|
|----------------|-----------------|
|`_String_length_(param)`|`param` je počet elementů v řetězec, který se má ale nezahrnuje ukončovací znak null. Tato poznámka je vyhrazený pro typy řetězce znaků.|
|`strlen(param)`|`param` je počet elementů v řetězec, který se má ale nezahrnuje ukončovací znak null. Tato poznámka je vyhrazený pro použití na znak pole a podobá se funkci C Runtime [strlen()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l).|
|`wcslen(param)`|`param` počet prvků v řetězci nahoru (ale nikoli včetně), které je ukončovacího znaku null. Tato poznámka je vyhrazený pro použití na široké znaky pole a podobá se funkci C Runtime [wcslen()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l).|

## <a name="see-also"></a>Viz také

- [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Porozumění SAL](../code-quality/understanding-sal.md)
- [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)
- [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)
- [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)
- [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Doporučené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)