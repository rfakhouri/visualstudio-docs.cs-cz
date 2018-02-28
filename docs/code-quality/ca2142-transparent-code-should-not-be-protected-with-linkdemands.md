---
title: "CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5d0094d8afa2dcf59efe0aace8514979d73ac921
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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