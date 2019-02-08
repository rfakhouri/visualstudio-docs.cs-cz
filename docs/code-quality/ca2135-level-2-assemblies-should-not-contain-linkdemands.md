---
title: 'CA2135: Sestavení úrovně 2 by neměla obsahovat LinkDemands'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fcd9032d550e79a47941540408dc6e98a15e33f7
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949509"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Sestavení úrovně 2 by neměla obsahovat LinkDemands

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Používá třídu nebo člen třídy <xref:System.Security.Permissions.SecurityAction> v aplikaci, která používá zabezpečení úrovně 2.

## <a name="rule-description"></a>Popis pravidla
 Pravidla LinkDemand jsou v sadě pravidel zabezpečení úrovně 2 již zastaralá. Namísto použití pravidel LinkDemand k vynucení zabezpečení v době kompilace just-in-time (JIT), označte metody, typy a pole s <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Security.Permissions.SecurityAction> a označit typ nebo člen se <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu <xref:System.Security.Permissions.SecurityAction> by měly být odstraněny a metodě označené <xref:System.Security.SecurityCriticalAttribute> atribut.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]