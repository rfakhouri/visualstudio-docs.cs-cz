---
title: QueryCounters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 15ee0aebd706dc7fbf21711a1e87d945aa2188d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="querycounters"></a>QueryCounters
**QueryCounters** možnost uvádí čítače výkonu procesoru (hardware), které jsou k dispozici v počítači.  
  
 **QueryCounters** musí být pouze možnost na příkazovém řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 Při použití metody instrumentace profileru může shromažďovat hodnoty jeden nebo více čítačů výkonu procesoru v každé události kolekce dat. Při použití metoda profilování se vzorkováním, můžete zadat jeden čítač událostí a počet výskytů události má být použit jako intervalu vzorkování.  
  
 Různé procesory zpřístupnit různé čítače výkonu procesoru. Profileru definuje sadu Obecné čítače, které lze použít na téměř všechny procesory. **QueryCounters** možnost uvádí názvy Obecné čítače i názvy čítačů, které jsou specifické pro procesor.  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)