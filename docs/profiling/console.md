---
title: Konzoly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9450254620fff8981aa9330dc41535ec69c0d842
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53944136"
---
# <a name="console"></a>Konzola
VSPerfCmd.exe **konzoly** možnost spustí aplikaci, která zadané v novém okně příkazového řádku. **Konzola** jde použít jenom s příkazu vsperfcmd proveďte **spuštění** možnost. Pokud aplikace není aplikace pomocí příkazového řádku **konzoly** nemá žádný vliv.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /Console  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádná  
  
## <a name="required-options"></a>Požadované možnosti  
 **Konzola** lze zadat pouze na příkazovém řádku, který také obsahuje **spuštění** možnost.  
  
 **Spuštění:** `AppName`  
 Spuštění profileru a aplikace určené `AppName`.  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)