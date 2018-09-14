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
ms.openlocfilehash: 2dbb5ba3fe1f16f5a05d01d25040de39370cddc8
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548310"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Použijte parametry pro proměnné argumenty
|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ obsahuje veřejná nebo chráněná metoda, která používá `VarArgs` konvence volání.

## <a name="rule-description"></a>Popis pravidla
 `VarArgs` Konvence volání se používá některé metody definicemi přijímajícími proměnný počet parametrů. Metoda použití `VarArgs` konvence volání není specifikace CLS (Common Language) předpisy a nemusí být přístupné napříč programovacími jazyky.

 V jazyce C# `VarArgs` konvence volání se používá při seznamu parametrů metod končí `__arglist` – klíčové slovo. Jazyk Visual Basic nepodporuje `VarArgs` volání konvence a Visual C++ umožňuje použití pouze v nespravovaném kódu, který používá tři tečky `...` zápis.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla v jazyce C#, použijte [params](/dotnet/csharp/language-reference/keywords/params) – klíčové slovo místo `__arglist`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva způsoby, ten, který porušuje pravidla a ten, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Reflection.CallingConventions?displayProperty=fullName>
- [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)