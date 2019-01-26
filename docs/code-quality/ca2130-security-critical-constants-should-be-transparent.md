---
title: 'CA2130: Konstanty kritické pro zabezpečení musí být transparentní'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d3b28e70b9f009ea1da9174319d3d72c5371911e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55019629"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Konstanty kritické pro zabezpečení musí být transparentní

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Konstanty pole nebo na člena výčtu je označeno <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Popis pravidla
 Pro konstantní hodnoty není vynucována transparentnost, protože kompilátory vkládají konstantní hodnoty do kódu, aby za běhu programu nebylo zapotřebí žádné vyhledávání. Konstantní pole by měla být transparentní z pohledu zabezpečení, aby kontroloři kódu nepředpokládali, že transparentní kód nemůže ke konstantě přistoupit.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte atribut SecurityCritical z pole nebo hodnoty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujících příkladech, hodnota výčtu `EnumWithCriticalValues.CriticalEnumValue` a konstanty `CriticalConstant` vyvolat toto upozornění. Chcete-li opravit problémy, odeberte [`SecurityCritical`] atribut, aby se daly zabezpečení transparentní.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]