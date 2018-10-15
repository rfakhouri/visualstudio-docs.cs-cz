---
title: QueryCounters | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ee9028f3fe4d72d70b2d9b6acab2c70705bfe40
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49175250"
---
# <a name="querycounters"></a>QueryCounters
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**QueryCounters** Vypíše seznam čítačů výkonu procesoru (hardware), které jsou k dispozici v počítači.  
  
 **QueryCounters** musí být jedinou možností příkazového řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 Při použití metody instrumentace profileru můžete shromažďovat hodnoty jedné nebo více čítačů výkonu procesoru na každou událost shromažďování dat. Při použití metoda profilování vzorkování, můžete zadat jeden čítače událostí a počet výskytů události má být použit jako interval vzorkování.  
  
 Různé procesory zveřejnit různé čítače výkonu procesoru. Profiler definuje sadu obecný čítače, které jde použít na téměř všechny procesory. **QueryCounters** Vypíše seznam názvů obecného čítače i názvy čítačů, které jsou specifické pro procesor.  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)



