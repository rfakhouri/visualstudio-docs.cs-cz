---
title: 'CA1064: Výjimky by měly být veřejné'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b17ccfe66875588ac19c587ff6fcbd889d1e6a44
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922321"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: Výjimky by měly být veřejné

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|Kategorie|Microsoft.Design|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Výjimka, která není veřejná, je odvozena <xref:System.Exception>přímo <xref:System.SystemException>z, <xref:System.ApplicationException>nebo.

## <a name="rule-description"></a>Popis pravidla
Vnitřní výjimka je viditelná pouze uvnitř vlastního vnitřního oboru. Jakmile výjimka přesáhne hranice vnitřního rozsahu, lze pro zachycení výjimky použít pouze základní výjimku. Pokud je vnitřní výjimka zděděna z <xref:System.Exception>, <xref:System.SystemException>, nebo <xref:System.ApplicationException>, externí kód nebude mít dostatečné informace o tom, co dělat, s výjimkou.

Nicméně, pokud má kód veřejnou výjimku, která je později použita jako základ pro vnitřní výjimku, je vhodné předpokládat, že kód bude další, je možné něco inteligentního se základní výjimkou. Veřejná výjimka bude obsahovat více informací <xref:System.Exception>, než jaké poskytuje, <xref:System.SystemException>nebo <xref:System.ApplicationException>.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Udělejte výjimku jako veřejné, nebo odvodit vnitřní výjimku z veřejné výjimky, která <xref:System.Exception>není, <xref:System.SystemException>nebo <xref:System.ApplicationException>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit zprávu z tohoto pravidla, pokud jste si jistí, že se soukromá výjimka zachytí v rámci vlastního vnitřního oboru.

## <a name="example"></a>Příklad
Toto pravidlo je vyvoláno v prvním příkladu metody FirstCustomException, protože třída výjimky je odvozena přímo z výjimky a je interní. Pravidlo se neaktivuje u třídy SecondCustomException, protože i když třída je odvozená také přímo z výjimky, třída je deklarována jako veřejná. Třetí třída také neaktivuje pravidlo, protože neodvozuje přímo z <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>nebo <xref:System.ApplicationException?displayProperty=fullName>.

[!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
