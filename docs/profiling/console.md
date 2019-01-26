---
title: Konzoly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e825ba66-1383-46ad-8712-396bc9c14036
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e1870870301b4f9812ea9a16fe6089fd72028b8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54987424"
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
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)