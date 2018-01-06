---
title: Konzole | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 31409c96a63a82898fcc999fa9f441a8c766b190
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
 **Spuštění:**`AppName`  
 Spustí profileru a aplikace určeného `AppName`.  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)