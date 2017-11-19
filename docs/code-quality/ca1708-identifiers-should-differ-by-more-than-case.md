---
title: "CA1708: Identifikátory by se měly lišit o více než případ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cda7936a1a701b1b51957a7038db496f70ddd9c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen
|||  
|-|-|  
|TypeName|IdentifiersShouldDifferByMoreThanCase|  
|CheckId|CA1708|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Názvy dva typy členů, parametrů nebo plně kvalifikovaný obory názvů jsou identické, když se převedou na malá písmena.  
  
## <a name="rule-description"></a>Popis pravidla  
 Identifikátory pro obory názvů, typy, členy a parametry nelze odlišit pouze ve velikosti písmen, protože jazyky cílené na modul CLR (Common Language Runtime) nemusí rozlišovat malá a velká písmena. Například [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] je často používaný jazyk velká a malá písmena.  
  
 Toto pravidlo aktivuje na veřejně viditelný pouze členy.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název, který je jedinečný, když se porovnává se další identifikátory způsobem velká a malá písmena.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Nemusí být použitelná ve všech jazycích k dispozici v knihovně [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
## <a name="example-of-a-violation"></a>Příkladem porušení  
 Následující příklad ukazuje narušení tohoto pravidla.  
  
 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)