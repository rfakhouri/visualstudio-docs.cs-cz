---
title: "CA2143: Transparentní metody nemohou používat požadavky zabezpečení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 22adac09d7890f9d15e0bf50f46235f4b48d73dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: Transparentní metody nemohou používat požadavky zabezpečení
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotDemand|  
|CheckId|CA2143|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Tranparent typ nebo metoda deklarativně označena <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` vyžádání nebo volání metod <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> metoda.  
  
## <a name="rule-description"></a>Popis pravidla  
 Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Kód transparentní z hlediska zabezpečení by měl k učinění rozhodnutí o zabezpečení používat úplné požadavky a bezpečně kritický kód by neměl spoléhat na to, že transparentní kód tyto úplné požadavky provede. Místo toho by měla být kritická kód, který provádí kontroly zabezpečení, jako je například požadavky na zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Obecně platí, chcete-li opravit porušení toto pravidlo, označit metodu s <xref:System.Security.SecuritySafeCriticalAttribute> atribut. Můžete také odebrat vyžádání.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Pravidlo soubory na následující kód, protože transparentní metoda provede požadavek deklarativní zabezpečení.  
  
 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../code-quality/codesnippet/CSharp/ca2143-transparent-methods-should-not-use-security-demands_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)