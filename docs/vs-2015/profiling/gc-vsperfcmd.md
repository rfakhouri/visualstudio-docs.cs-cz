---
title: Uvolňování paměti (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2bdb28f74dd305dc497521e95d38e00192c21c54
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68193606"
---
# <a name="gc-vsperfcmd"></a>Uvolňování paměti (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**GC** možnost povoluje shromažďování dat rozhraní .NET Framework paměť přidělení a objekt životnost. **Uvolňování paměti** možnost jde použít jenom s metoda profilování vzorkování a jenom **spuštění** možnost.  
  
 Při použití **GC** možnost, VSPerfClrEnv **/sampleon** příkazu se nevyžaduje.  
  
 Pokud nejsou zadány žádné parametry, nebo pokud **přidělení** parametr zadán, jsou shromažďovány pouze rozhraní .NET Framework data o přidělování paměti. Pokud **životnost** parametr zadán, přidělení paměti rozhraní .NET Framework a .NET Framework objekt se shromažďují data o životním cyklu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 **přidělení**  
 Default (Výchozí). Shromažďuje data o přidělování paměti rozhraní .NET Framework.  
  
 **Doba platnosti**  
 Shromažďuje data o přidělování paměti rozhraní .NET Framework a .NET Framework data o životním cyklu objektu.  
  
## <a name="required-options"></a>Požadované možnosti  
 **GC** možnost se dá použít jenom s **spuštění** možnost.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí aplikaci a shromažďuje data o přidělování paměti rozhraní .NET Framework.  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Viz také  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
