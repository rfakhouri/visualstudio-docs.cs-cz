---
title: Řešení potíží s Analýzou kódu
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9029c7be21fe02b9d6b1c4436658df74eb3c37f9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
Toto téma obsahuje informace o odstraňování potíží pro následující problémy analýzy kódu aplikace Visual Studio.

-   [Změny v Visual Studio 2010 pravidlo sady jsou není v předchozích verzích sady Visual Studio](#ChildRuleSetChangesInPreviousVersions)

##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Změny v Visual Studio 2010 pravidlo sady jsou není v předchozích verzích sady Visual Studio
 Když vytvoříte pravidlo nastavené v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] obsahující podřízenou sadu pravidel, ke změně je sada pravidel pro podřízené nemusí být pro spuštění analýzy kódu na počítačích, které používají starší verze sady Visual Studio. Chcete-li vyřešit tento problém, musíte Vynutit přepsání sadu pravidel nadřazené, který je sada pravidel, která obsahuje podřízenou sadu pravidel.

1.  Otevřete nadřazené pravidlo nastavené [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

2.  Změňte, například přidávání nebo odebírání pravidlo a potom uložte sadu pravidel.

3.  Otevřete sadu pravidel, zrušení změny a potom uložte pravidlo znovu nastavit.

## <a name="see-also"></a>Viz také
 [Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md) [analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md) [použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)