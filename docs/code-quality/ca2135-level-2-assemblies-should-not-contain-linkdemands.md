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
ms.openlocfilehash: d466a508eade835563627a829f937416a24972a0
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920641"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Sestavení úrovně 2 by neměla obsahovat LinkDemands

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Člen třídy nebo třídy používá <xref:System.Security.Permissions.SecurityAction> v aplikaci, která používá zabezpečení úrovně 2.

## <a name="rule-description"></a>Popis pravidla
Pravidla LinkDemand jsou v sadě pravidel zabezpečení úrovně 2 již zastaralá. Namísto použití LinkDemand k vymáhání zabezpečení při kompilaci za běhu, označte metody, typy a pole <xref:System.Security.SecurityCriticalAttribute> atributem.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Security.Permissions.SecurityAction> a označte typ nebo člen <xref:System.Security.SecurityCriticalAttribute> s atributem.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
V následujícím příkladu <xref:System.Security.Permissions.SecurityAction> by měla být odebrána a metoda označená <xref:System.Security.SecurityCriticalAttribute> atributem.

[!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]