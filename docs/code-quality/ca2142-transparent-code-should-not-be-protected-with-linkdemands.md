---
title: 'CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 969c4f73148401f0a4f389f86b866023c316298c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919341"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands
|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Transparentní metoda vyžaduje, <xref:System.Security.Permissions.SecurityAction> nebo další požadavek zabezpečení.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno na transparentních metodách, které vyžadují pro přístup k nim pravidla LinkDemand. Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Protože transparentní metody jsou by měl být neutrální zabezpečení, se nesmí při rozhodování žádné zabezpečení. Kromě toho by neměl být bezpečné kritické kód, který rozhodnutí zabezpečení, spoléhat na kód transparentní pro toto rozhodnutí provedli dříve.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odeberte požadavek propojení na metodě transparentní nebo označit metodu s <xref:System.Security.SecuritySafeCriticalAttribute> kontroluje atribut v případě, že je její výkon na zabezpečení, jako je například požadavky na zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 V následujícím příkladu, pravidlo aktivuje na metodu, protože metoda je transparentní a je označené jako LinkDemand <xref:System.Security.PermissionSet> obsahující <xref:System.Security.Permissions.SecurityAction>.

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]

 Nepotlačujte upozornění na toto pravidlo.