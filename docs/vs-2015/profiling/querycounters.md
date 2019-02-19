---
title: QueryCounters | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cdd2707a6af2b9d03e73c696884dc12413437b04
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54760122"
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
 Žádná  
  
## <a name="remarks"></a>Poznámky  
 Při použití metody instrumentace profileru můžete shromažďovat hodnoty jedné nebo více čítačů výkonu procesoru na každou událost shromažďování dat. Při použití metoda profilování vzorkování, můžete zadat jeden čítače událostí a počet výskytů události má být použit jako interval vzorkování.  
  
 Různé procesory zveřejnit různé čítače výkonu procesoru. Profiler definuje sadu obecný čítače, které jde použít na téměř všechny procesory. **QueryCounters** Vypíše seznam názvů obecného čítače i názvy čítačů, které jsou specifické pro procesor.  
  
## <a name="see-also"></a>Viz také  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
