---
title: Sys (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81661358dbc000f871015099ab40ee8bbfb56195
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
VSPerfCmd.exe **Sys** možnost nastaví profilování událost, která je vzorků na volání události systému (funkce volání z aplikace PROFILOVANÉHO v operačním systému) a volitelně změny číslo systému volání v vzorky Interval z výchozí hodnotu 10.  
  
 **Sys** lze použít pouze v příkazovém řádku, který také obsahuje **spusťte** nebo **Attach** možnost.  
  
 Ve výchozím nastavení událostí vzorkování profileru nastavena na výkon procesoru hodiny a interval vzorkování je nastaven na hodnotu 10 000 000. **Časovače**, **PF**, **Sys**, a **čítač** možnosti umožňují nastavit událostí vzorkování a intervalu vzorkování. **GC** možnost shromažďuje data paměti .NET v každé kolekci události přidělení a uvolňování paměti. Na příkazovém řádku lze zadat pouze jeden z těchto možností.  
  
 Vzorkování událostí a intervalu vzorkování lze nastavit pouze v první příkazového řádku, který obsahuje **spusťte** nebo **Attach** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Events`  
 Celočíselná hodnota, která určuje počet systému volání události v intervalu vzorkování. Pokud `Events` není zadán, interval je nastaven na hodnotu 10.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Sys** vyžaduje jednu z následujících možností.  
  
 **Spusťte:** `AppName`  
 Spustí profileru a aplikace určeného `AppName`.  
  
 **Připojení:** `PID`  
 Připojí k proces zadaný pomocí profileru `PID`.  
  
## <a name="invalid-options"></a>Neplatné možnosti  
 Nelze zadat následující možnosti na stejném příkazovém řádku jako **Sys**.  
  
 **PF**[**:**`Events`]  
 Nastaví událostí vzorkování na chyb stránek a volitelně nastaví interval vzorkování na `Events`. Výchozí interval PF je 10.  
  
 **Časovač**[**:**`Cycles`]  
 Nastaví vzorkování události hodin procesoru cyklů a volitelně nastaví interval vzorkování na `Cycles`. Výchozí hodnota intervalu časovače je 10 000 000.  
  
 **Čítač:** `Name`[`,Reload`[`,FriendlyName`]]  
 Nastaví událostí vzorkování na výkon procesoru čítač určeného `Name` a nastaví interval vzorkování na `Reload`.  
  
 **Globální Katalog**[**:**{**přidělení**&#124;**životnost**}]  
 Shromažďuje data paměti .NET. Ve výchozím nastavení (**přidělení**), data jsou shromažďována v každé události přidělení paměti. Když **životnost** je zadán parametr, data jsou shromažďována také v každé události kolekce paměti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak nastavit událostí vzorkování profileru na systémová volání a jak nastavit interval vzorkování na 20 volání za ukázka.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)