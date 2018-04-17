---
title: 'CA2135: Sestavení úrovně 2 nesmějí obsahovat LinkDemands | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0be276db088e30a71e40905423c5c88a5b714d43
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Sestavení úrovně 2 nesmějí obsahovat LinkDemands
|||  
|-|-|  
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|  
|CheckId|CA2135|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Třída nebo člen třídy používá <xref:System.Security.Permissions.SecurityAction> v aplikaci, která používá zabezpečení Level 2.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pravidla LinkDemand jsou v sadě pravidel zabezpečení úrovně 2 již zastaralá. Místo použití LinkDemands vynutit zabezpečení v době kompilace za běhu (JIT), označit metody, typy a pole s <xref:System.Security.SecurityCriticalAttribute> atribut.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte <xref:System.Security.Permissions.SecurityAction> a označit typ nebo člen s <xref:System.Security.SecurityCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu <xref:System.Security.Permissions.SecurityAction> měla by být odebrána a označené jako metodu <xref:System.Security.SecurityCriticalAttribute> atribut.  
  
 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]