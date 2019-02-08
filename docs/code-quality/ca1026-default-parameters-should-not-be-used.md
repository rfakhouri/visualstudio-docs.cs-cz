---
title: 'CA1026: Neměly by být použity výchozí parametry'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5dc7f7e62526050eeabdb91a557bbdf0fbcf6da
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957949"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: Neměly by být použity výchozí parametry

|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Externě viditelný typ obsahuje externě viditelná metoda, která používá výchozí parametr.

## <a name="rule-description"></a>Popis pravidla
 Metody používající výchozí parametry jsou povoleny v rámci specifikace CLS (Common Language); ale specifikace CLS umožňuje kompilátorům Ignorovat hodnoty přiřazené těmto parametrům. Kód, který je napsán pro kompilátory, které ignorovat výchozí hodnoty parametrů musíte explicitně zadat argumenty pro každý parametr výchozí. Chcete-li zachovat shodné chování napříč programovacími jazyky, by měl vyměnit metody používající výchozí parametry přetížením metody, která výchozí parametry poskytují.

 Kompilátor ignoruje hodnoty výchozí parametry pro spravované rozšíření jazyka C++ při přístupu ke spravovaným kódem. Kompilátor jazyka Visual Basic podporuje metody, které mají výchozí parametry, které používají [volitelné](/dotnet/visual-basic/language-reference/modifiers/optional) – klíčové slovo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, nahraďte metody používající výchozí parametry přetížením metody, které poskytují výchozí parametry.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která používá výchozí hodnoty parametrů a přetížené metody, které poskytují ekvivalentní funkce.

 [!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1025: Nahraďte opakované argumenty polem](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>Viz také:
 [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)