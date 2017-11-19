---
title: "CA1719: Názvy parametrů by neměly odpovídat názvům členů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 03c6459a4f879dce0f03e3516601e64c53d44b33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719: Názvy parametrů by neměly odpovídat názvům členů
|||  
|-|-|  
|TypeName|ParameterNamesShouldNotMatchMemberNames|  
|CheckId|CA1719|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název člena externě viditelné odpovídá v porovnávání, název jednoho z jeho parametrů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Název parametru by měl sdělit význam parametru a název členu by měl sdělit význam členu. Byl by to vzácný návrh, pokud by byly stejné. Stejné pojmenování parametru i jeho členu je neintuitivní a činí knihovnu obtížně použitelnou.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název parametru, která neodpovídá název člena.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pro nový vývoj žádné známé scénáře nastat, kde je třeba potlačit upozornění na toto pravidlo. Pro přesouvání knihovny, můžete chtít potlačit upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit o více než případu](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)