---
title: LineOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0bde53a409428d140afe498c2894e93e1355726
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="lineoff"></a>LineOff
Ve výchozím nastavení profileru shromažďuje zdrojový kód řádku číslo a řádku číslo posunutí data při použití metoda profilování se vzorkováním. VSPerfCmd **LineOff** možnost zakáže shromažďování dat číslo řádku, pokud je VSPerfCmd se používá ke spuštění aplikace. Profilace data se shromažďují funkce úrovni při **LineOff** je zadán.  
  
 Můžete použít **LineOff** pouze s **spusťte** možnost, a pouze když profileru byl inicializován pro vzorkování pomocí **spustit**:**ukázka** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="required-options"></a>Požadované možnosti  
 **LineOff** možnost lze použít pouze na příkazový řádek, který obsahuje **spusťte** možnost.  
  
 **Spusťte:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
## <a name="example"></a>Příklad  
 Tento příkaz spustí aplikace a profileru a zakáže vzorkování na úrovni řádku.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)