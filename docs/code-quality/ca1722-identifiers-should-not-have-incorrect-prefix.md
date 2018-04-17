---
title: 'CA1722: Identifikátory by neměly mít nesprávnou předponu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e95ef8daa7ed7fc7da4de4b99c677ef92559acb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Identifikátory by neměly mít nesprávnou předponu
|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|  
|CheckId|CA1722|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Identifikátor má nesprávnou předponu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Podle konvence mají pouze některé programovací prvky názvy začínající určitou předponou.  
  
 Názvy typů nemají konkrétní předpony a nesmí obsahovat předponu "C". Toto pravidlo sestavy porušení pro typ názvy, například "CMyClass a nevytváří sestavu porušení pro typ názvy, například 'Mezipaměti'.  
  
 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odebrání identifikátor předponu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1715: Identifikátory by měly mít správnou předponu](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)