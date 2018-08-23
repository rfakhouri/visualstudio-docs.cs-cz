---
title: Řešení potíží s problémy s analýzou kódu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: 7
author: erickson-doug
ms.author: gewarren
manager: douge
ms.openlocfilehash: b8d17fcaec0034d2803f769cc5595416f5d56de8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672516"
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [řešení potíží s problémy s analýzou kódu](https://docs.microsoft.com/visualstudio/code-quality/troubleshooting-code-analysis-issues).  
  
Toto téma obsahuje informace o odstraňování potíží pro následující problémy s analýzou kódu sady Visual Studio.  
  
-   [Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio  
 Když vytvoříte pravidlo nastavit [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] , která obsahuje podřízenou sadu pravidel, nejde použít ke změně podřízené sady pravidel v nastavují spuštění analýzu kódu na počítačích, které používají starší verzi sady Visual Studio. Pokud chcete tento problém vyřešit, musíte Vynutit přepsání sady pravidel nadřazený, který je sada pravidel, která obsahuje podřízené sady pravidel.  
  
1.  Otevřít nadřazený pravidlo nastavené [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].  
  
2.  Proveďte změnu, jako je například přidávání nebo odebírání pravidlo a potom uložte sady pravidel.  
  
3.  Znovu otevřít sadu pravidel, zrušení změny a potom uložte pravidlo znovu nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Analýza kvality aplikace](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [Analýza kvality spravovaného kódu](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)



