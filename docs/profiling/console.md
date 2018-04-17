---
title: Konzole | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdde25fdba4c227a5e46d33eeca356d4335d2eb7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="console"></a>Konzola
VSPerfCmd.exe **konzoly** možnost spuštění zadaná aplikace v novém okně příkazového řádku. **Konzole** lze použít pouze s VSPerfCmd **spusťte** možnost. Pokud aplikace není aplikace pomocí příkazového řádku **konzoly** nemá žádný vliv.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="required-options"></a>Požadované možnosti  
 **Konzole** lze zadat pouze na příkazový řádek, který obsahuje také **spusťte** možnost.  
  
 **Spusťte:** `AppName`  
 Spustí profileru a aplikace určeného `AppName`.  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)