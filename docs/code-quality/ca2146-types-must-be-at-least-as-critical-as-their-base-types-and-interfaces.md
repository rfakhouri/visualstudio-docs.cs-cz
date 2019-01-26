---
title: 'CA2146: Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8bfc3cebb0d90d0400f1b5dbd1c9ba6bab266563
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014091"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní

|||
|-|-|
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|
|CheckId|CA2146|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Transparentní typ je odvozen od typu, který je označen <xref:System.Security.SecuritySafeCriticalAttribute> nebo <xref:System.Security.SecurityCriticalAttribute>, nebo typ, který je označen <xref:System.Security.SecuritySafeCriticalAttribute> atribut je odvozen z typu, který je označen pomocí <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno, když má odvozený typ atribut transparentnosti zabezpečení, který není tak kritický jako jeho základní typ nebo implementované rozhraní. Pouze kritické typy lze odvodit z kritických základních typů nebo mohou implementovat kritická rozhraní a pouze kritické typy nebo bezpečně kritické typy mohou být odvozeny ze základních bezpečně kritických typů nebo mohou implementovat bezpečně kritická rozhraní. Za následek porušení tohoto pravidla v transparentnosti úrovně 2 <xref:System.TypeLoadException> pro odvozeného typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit toto porušení, označte odvozené nebo implementující typ s atributem transparentnosti, která jsou kritická jako základní typ nebo rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]