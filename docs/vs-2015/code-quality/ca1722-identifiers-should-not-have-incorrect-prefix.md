---
title: 'CA1722: Identifikátory by neměly mít nesprávnou předponu | Dokumentace Microsoftu'
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
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6e218f4c9abb86fb5115a1df4fb6f66bb1856e16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666861"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Identifikátory by neměly mít nesprávnou předponu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1722: identifikátory by neměly mít nesprávnou předponu](https://docs.microsoft.com/visualstudio/code-quality/ca1722-identifiers-should-not-have-incorrect-prefix).  
  
TypeName | IdentifiersShouldNotHaveIncorrectPrefix |  
| ID kontroly | CA1722 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Identifikátor má nesprávnou předponu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Podle konvence mají pouze některé programovací prvky názvy začínající určitou předponou.  
  
 Názvy typů nemusí specifický prefix a by neměly mít předponu 'C'. Toto pravidlo oznámí porušení zásad pro názvy typů, jako je například "CMyClass" a nevytváří sestavu porušení zásad pro názvy typů, jako je například "Mezipaměti".  
  
 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odebrání předpony identifikátoru.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1715: Identifikátory by měly mít správnou předponu](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)



