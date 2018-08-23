---
title: 'CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3a5b13185077e8951a6959be33f92c451eaaf0c3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628706"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2142: transparentní kód nemůže být chráněn pomocí LinkDemands](https://docs.microsoft.com/visualstudio/code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands).  
  
TypeName | TransparentMethodsShouldNotBeProtectedWithLinkDemands |  
| ID kontroly | CA2142 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Transparentní metoda vyžaduje, <xref:System.Security.Permissions.SecurityAction> nebo další požadavek zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je vyvoláno na transparentních metodách, které vyžadují pro přístup k nim pravidla LinkDemand. Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Protože transparentní metody mají být zabezpečení neutrální, jejich by neměla provádět rozhodnutí o zabezpečení. Kromě toho by neměl být bezpečně kritický kód, který rozhodování zabezpečení, spoléhat na transparentnímu kódu dříve provedli tato rozhodnutí.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, odeberte požadavek propojení na transparentní metodu nebo označte metodu s <xref:System.Security.SecuritySafeCriticalAttribute> kontroly atribut, pokud se provádí zabezpečení, jako jsou požadavky na zabezpečení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu pravidlo je vyvoláno na metodě vzhledem k tomu, že metoda je transparentní a je označená pomocí LinkDemand <xref:System.Security.PermissionSet> , který obsahuje <xref:System.Security.Permissions.SecurityAction>.  
  
 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]  
  
 Nepotlačujte upozornění na toto pravidlo.



