---
title: 'CA2230: Použijte parametry pro proměnné argumenty'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 505aa8cdc1371a3bc288772d77b49eb7a50e9830
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920143"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Použijte parametry pro proměnné argumenty

|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo chráněný typ obsahuje veřejnou nebo chráněnou metodu, která používá `VarArgs` konvenci volání.

## <a name="rule-description"></a>Popis pravidla
Konvence `VarArgs` volání se používá s určitými definicemi metod, které přebírají proměnný počet parametrů. Metoda používající `VarArgs` konvenci volání není kompatibilní se specifikací CLS (Common Language Specification) a nemusí být přístupná v různých programovacích jazycích.

V C#je konvence `VarArgs` volání použita v případě, že `__arglist` seznam parametrů metody končí klíčovým slovem. Visual Basic nepodporuje konvenci C++ `...` voláníavizuálumožňujejehopoužitípouzevnespravovanémkódu,kterýpoužívátřitečky`VarArgs` .

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla C#, použijte `__arglist`klíčové slovo [params](/dotnet/csharp/language-reference/keywords/params) namísto.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad ukazuje dvě metody, jeden, který porušuje pravidlo a jeden, který splňuje pravidlo.

[!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Reflection.CallingConventions?displayProperty=fullName>
- [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)