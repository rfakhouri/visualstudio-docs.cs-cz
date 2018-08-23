---
title: LineOff | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cf55f34b1ced4d76dcd45ea08514dfbb04ca582b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669438"
---
# <a name="lineoff"></a>LineOff
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [LineOff](https://docs.microsoft.com/visualstudio/profiling/lineoff).  
  
Ve výchozím nastavení profiler shromažďuje zdrojového kódu řádek číslo a řádek číslo posunu data při použití metoda profilování vzorkování. Příkazu vsperfcmd proveďte **LineOff** možnost zakazuje shromažďování dat číslo řádku, když, VSPerfCmd se používá ke spuštění aplikace. Funkce jsou shromažďována data profilování úrovni v případě **LineOff** určena.  
  
 Můžete použít **LineOff** pouze s **spuštění** možnost, a pouze pokud profiler byl inicializován pro vzorkování pomocí **Start**:**ukázka** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="required-options"></a>Požadované možnosti  
 **LineOff** možnost použít jenom na příkazovém řádku, který obsahuje **spuštění** možnost.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí aplikaci a profiler a zakáže vzorkování na úrovni řádku.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)



