---
title: 'CA2230: Použijte parametry pro proměnné argumenty'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70492152e75d3d257b63e014e854c4b0b431d2ec
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917715"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Použijte parametry pro proměnné argumenty
|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ veřejné nebo chráněného obsahuje veřejný nebo chráněné metody, která používá `VarArgs` konvence volání.

## <a name="rule-description"></a>Popis pravidla
 `VarArgs` Konvence volání se používá s určitým metoda definice, které trvat proměnný počet parametrů. Metoda pomocí `VarArgs` konvence volání není specifikace CLS (Common Language) kompatibilní a nemusí být dostupné v rámci programovacích jazyků.

 V jazyce C# `VarArgs` konvence volání se používá při seznam parametrů metoda končí `__arglist` – klíčové slovo. Visual Basic nepodporuje `VarArgs` volání konvence a Visual C++ umožňuje jeho použití pouze v nespravovaném kódu, který používá se třemi tečkami `...` zápis.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla v jazyku C#, použijte [parametry](/dotnet/csharp/language-reference/keywords/params) – klíčové slovo místo `__arglist`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva způsoby, jednu, která porušuje pravidlo a ten, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Reflection.CallingConventions?displayProperty=fullName> [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)