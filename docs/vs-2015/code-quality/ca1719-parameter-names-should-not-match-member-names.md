---
title: 'CA1719: Názvy parametrů by neměly odpovídat názvům členů | Dokumentace Microsoftu'
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
- ParameterNamesShouldNotMatchMemberNames
- CA1719
helpviewer_keywords:
- CA1719
- ParameterNamesShouldNotMatchMemberNames
ms.assetid: c6fea690-1659-4ee7-a1c5-125ad6754525
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 17c7cafa69f067e031b6bbf7d204bdcb1d96a3e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632618"
---
# <a name="ca1719-parameter-names-should-not-match-member-names"></a>CA1719: Názvy parametrů by neměly odpovídat názvům členů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1719: názvy parametrů by neměly odpovídat názvům členů](https://docs.microsoft.com/visualstudio/code-quality/ca1719-parameter-names-should-not-match-member-names).  
  
TypeName | ParameterNamesShouldNotMatchMemberNames |  
| ID kontroly | CA1719 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Název externě viditelného členu odpovídá v porovnávání, název jednoho ze svých parametrů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Název parametru by měl sdělit význam parametru a název členu by měl sdělit význam členu. Byl by to vzácný návrh, pokud by byly stejné. Stejné pojmenování parametru i jeho členu je neintuitivní a činí knihovnu obtížně použitelnou.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název parametru se neshoduje s názvem člena.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pro vývoj nových projektů, žádné známé scénáře nastat, pokud je třeba potlačit upozornění tohoto pravidla. Pro přesouvání knihovny, budete muset potlačit upozornění tohoto pravidla.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)



