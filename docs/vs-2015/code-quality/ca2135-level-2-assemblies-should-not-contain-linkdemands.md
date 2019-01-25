---
title: 'CA2135: Sestavení úrovně 2 nesmějí obsahovat LinkDemands | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cd4b1cb9d69e916a3d5cd547b3ff3714a20a665f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786516"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Sestavení úrovně 2 by neměla obsahovat LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Používá třídu nebo člen třídy <xref:System.Security.Permissions.SecurityAction> v aplikaci, která používá zabezpečení úrovně 2.

## <a name="rule-description"></a>Popis pravidla
 Pravidla LinkDemand jsou v sadě pravidel zabezpečení úrovně 2 již zastaralá. Namísto použití pravidel LinkDemand k vynucení zabezpečení v době kompilace just-in-time (JIT), označte metody, typy a pole s <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Security.Permissions.SecurityAction> a označit typ nebo člen se <xref:System.Security.SecurityCriticalAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu <xref:System.Security.Permissions.SecurityAction> by měly být odstraněny a metodě označené <xref:System.Security.SecurityCriticalAttribute> atribut.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135.cs#1)]
