---
title: 'CA1707: Identifikátory by neměly obsahovat podtržítka | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7973646aab545484287f5628eb0fa3cf3629db84
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189209"
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707: Identifikátory by neměly obsahovat podtržítka
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [CA1707: Identifikátory by neměly obsahovat podtržítka](https://docs.microsoft.com/visualstudio/code-quality/ca1707-identifiers-should-not-contain-underscores).  
  
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Zásadní – při aktivaci pro sestavení<br /><br /> Bez konce – při aktivaci pro parametry typu|  
  
## <a name="cause"></a>příčina  
 Název identifikátoru obsahuje znak podtržítka (_).  
  
## <a name="rule-description"></a>Popis pravidla  
 Názvy identifikátorů podle konvence neobsahují znak podtržítka (_). Toto pravidlo kontroluje obory názvů, typy, členy a parametry.  
  
 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte všechny znaky podtržítka z názvu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
