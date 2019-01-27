---
title: QueryCounters | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ada22ed251a09ca1422c952f43889bad7a1d3e8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961085"
---
# <a name="querycounters"></a>QueryCounters
**QueryCounters** Vypíše seznam čítačů výkonu procesoru (hardware), které jsou k dispozici v počítači.  
  
 **QueryCounters** musí být jedinou možností příkazového řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádná  
  
## <a name="remarks"></a>Poznámky  
 Při použití metody instrumentace profileru můžete shromažďovat hodnoty jedné nebo více čítačů výkonu procesoru na každou událost shromažďování dat. Při použití metoda profilování vzorkování, můžete zadat jeden čítače událostí a počet výskytů události má být použit jako interval vzorkování.  
  
 Různé procesory zveřejnit různé čítače výkonu procesoru. Profiler definuje sadu obecný čítače, které jde použít na téměř všechny procesory. **QueryCounters** Vypíše seznam názvů obecného čítače i názvy čítačů, které jsou specifické pro procesor.  
  
## <a name="see-also"></a>Viz také:  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)