---
title: 'CA2151: Pole s kritickými typy by měla být kritická pro zabezpečení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09db9d25-7d58-4725-a252-4a07baadf046
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 40a3f0b19400794b75d1d3b5028bb5123314690f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666210"
---
# <a name="ca2151-fields-with-critical-types-should-be-security-critical"></a>CA2151: Pole s kritickými typy by měla být kritická pro zabezpečení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2151: pole s kritickými typy by měla být kritická pro zabezpečení](https://docs.microsoft.com/visualstudio/code-quality/ca2151-fields-with-critical-types-should-be-security-critical).  
  
TypeName ||  
| ID kontroly | CA2151 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
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
  
 V tomto příkladu `m_field` je bezpečnostně transparentní pole typu, který je kritický pro zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Chcete-li používat typy kritické z hlediska zabezpečení, musí být kód, který odkazuje na typ, buď kritický z hlediska zabezpečení, nebo bezpečně kritický z hlediska zabezpečení. To platí i v případě, že je odkaz nepřímý. Například při odkazu na transparentní pole kritického typu musí být váš kód buď kritický z hlediska zabezpečení, nebo bezpečný z hlediska zabezpečení. Proto je existence transparentního pole kritického z hlediska zabezpečení nebo transparentního pole bezpečně kritického z hlediska zabezpečení zavádějící, jelikož transparentní kód nebude mít k poli přístup.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, označte pole s <xref:System.Security.SecurityCriticalAttribute> atribut, nebo změňte typ, který je odkazován zabezpečení tomto pole průhledného nebo bezpečně kritické.  
  
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
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145 - transparentmethodsshouldnotusesuppressunmanagedcodesecurity.cs#1)]  
  
### <a name="comments"></a>Komentáře



