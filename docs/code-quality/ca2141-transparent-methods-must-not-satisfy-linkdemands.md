---
title: CA2141:Transparentní metody nesmějí vyhovovat LinkDemands
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6bb38d11ca7312a7eda2ec4b516ab384741f9ab7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917289"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141:Transparentní metody nesmějí vyhovovat LinkDemands
|||
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Zabezpečení transparentní metoda volá metodu v sestavení, které není označen atributem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> splňuje atribut (APTCA) nebo metodu transparentní pro zabezpečení <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` pro určitý typ nebo metoda.

## <a name="rule-description"></a>Popis pravidla
 Neodpovídající LinkDemand je citlivé operace zabezpečení, což může způsobit nechtěné zvýšení oprávnění. Kód transparentní pro zabezpečení nesmějí vyhovovat LinkDemands, protože není vztahují stejné požadavky auditu zabezpečení jako kód kritický pro zabezpečení. Transparentní metody v sestaveních úroveň 1 sadu pravidel zabezpečení způsobí, že všechny LinkDemands splňují má být převeden na úplné požadavky za běhu, což může způsobit problémy s výkonem. V sestavení úrovně 2 sadu pravidel zabezpečení se nepodaří transparentní metody pokoušejí vyhovět LinkDemand, kompilovat v kompilátoru za běhu (JIT).

 V sestavení tohoto usee 2 úroveň zabezpečení, pokusy o zabezpečení transparentní metodu pro uspokojení LinkDemand nebo volání metody v sestavení bez APTCA vyvolá <xref:System.MethodAccessException>; v sestavení úrovně 1 LinkDemand stane úplný požadavek.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, označte přístupem metoda s <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut, nebo odeberte LinkDemand z metody přístupu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V tomto příkladu se pokusí zavolat metodu, která má LinkDemand transparentní metody. Toto pravidlo bude platit na tento kód.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]