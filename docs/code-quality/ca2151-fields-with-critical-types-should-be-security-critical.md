---
title: "CA2151: Pole s kritickými typy by měla být kritické pro zabezpečení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a703dec98c93c03a2df51d3bd3d4ecf870f2031
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: Pole s kritickými typy by měla být kritická pro zabezpečení
|||  
|-|-|  
|TypeName||  
|CheckId|CA2151|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Je deklarováno z hlediska zabezpečení transparentní pole nebo bezpečně kritické pole. Jeho typ je určen jako kritický z hlediska zabezpečení. Příklad:  
  
```csharp  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      Type1 m_field; // CA2151, transparent field of critical type  
   }  
  
```  
  
 V tomto příkladu `m_field` je transparentní pole zabezpečení typu, který je kritické pro zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Chcete-li používat typy kritické z hlediska zabezpečení, musí být kód, který odkazuje na typ, buď kritický z hlediska zabezpečení, nebo bezpečně kritický z hlediska zabezpečení. To platí i v případě, že je odkaz nepřímý. Například při odkazu na transparentní pole kritického typu musí být váš kód buď kritický z hlediska zabezpečení, nebo bezpečný z hlediska zabezpečení. Proto je existence transparentního pole kritického z hlediska zabezpečení nebo transparentního pole bezpečně kritického z hlediska zabezpečení zavádějící, jelikož transparentní kód nebude mít k poli přístup.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, označte pole s <xref:System.Security.SecurityCriticalAttribute> atribut, nebo zkontrolujte typ, který je odkazován objektem zabezpečení eith pole průhledných nebo bezpečné kritické.  
  
```csharp  
// Fix 1: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   [SecurityCritical]  
   class Type1 { } // Security Critical type  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
// Fix 2: Make the referencing field security critical  
[assembly: AllowPartiallyTrustedCallers]  
  
   class Type1 { } // Type1 is now transparent  
  
   class Type2 // Security transparent type  
   {  
      [SecurityCritical]  
      Type1 m_field; // Fixed: critical type, critical field  
   }  
  
```  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../code-quality/codesnippet/CSharp/ca2151-fields-with-critical-types-should-be-security-critical_1.cs)]  
  
### <a name="comments"></a>Komentáře