---
title: "Potíží s analýzou kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e552570eb48b9210b366ebbfe157fe656ab3fe0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
Toto téma obsahuje informace o odstraňování potíží pro následující problémy analýzy kódu aplikace Visual Studio.  
  
-   [Změny v Visual Studio 2010 pravidlo sady jsou není v předchozích verzích sady Visual Studio](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a>Změny v Visual Studio 2010 pravidlo sady jsou není v předchozích verzích sady Visual Studio  
 Když vytvoříte pravidlo nastavené v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] obsahující podřízenou sadu pravidel, ke změně je sada pravidel pro podřízené nemusí být pro spuštění analýzy kódu na počítačích, které používají starší verze sady Visual Studio. Chcete-li vyřešit tento problém, musíte Vynutit přepsání sadu pravidel nadřazené, který je sada pravidel, která obsahuje podřízenou sadu pravidel.  
  
1.  Otevřete nadřazené pravidlo nastavené [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].  
  
2.  Změňte, například přidávání nebo odebírání pravidlo a potom uložte sadu pravidel.  
  
3.  Otevřete sadu pravidel, zrušení změny a potom uložte pravidlo znovu nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)