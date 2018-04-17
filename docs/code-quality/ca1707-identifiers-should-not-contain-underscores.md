---
title: 'CA1707: Identifikátory by neměly obsahovat podtržítka | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22c911f90e4da45ce847654f0c89455375ea478e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707: Identifikátory by neměly obsahovat podtržítka
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Ukončování řádků - při sestavení<br /><br /> Bez ukončování - při parametry typu|  
  
## <a name="cause"></a>příčina  
 Název identifikátoru obsahuje znak podtržítka (_).  
  
## <a name="rule-description"></a>Popis pravidla  
 Názvy identifikátorů podle konvence neobsahují znak podtržítka (_). Toto pravidlo zkontroluje obory názvů, typy, členů a parametry.  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odeberte všechny podtržítka znaky z názvu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)