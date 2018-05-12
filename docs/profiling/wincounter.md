---
title: WinCounter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4751d44afc2f54ea57866e3674a5bc150444088b
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="wincounter"></a>WinCounter
**WinCounter** možnost určuje Windows nebo čítač výkonu aplikace během spuštění profilu shromažďovat ve stanovených intervalech. Systém Windows a čítače výkonu aplikace jsou uvedeny jako značky v profilaci datového souboru. Můžete určit více čítačů výkonu ke shromažďování v samostatné možnosti.  
  
 Ve výchozím nastavení, jsou shromažďovány čítače každých 500 milisekund. Použití **pro automatické označování** možnost zadat interval jinou kolekci.  
  
 Pouze jeden **pro automatické označování** možnost se používá. Pokud je to více **pro automatické označování** možnosti jsou určena, bude použita jako poslední.  
  
 **WinCounter** možnost lze použít pouze s **spustit** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Path`  
 Čítač výkonu systému Windows ve formátu cesta PDH čítače.  
  
## <a name="required-options"></a>Požadované možnosti  
 **WinCounter** možnost lze použít pouze s **spustit** možnost.  
  
 **Spusťte:** `Method`  
 **Spustit** možnost inicializuje profileru pro zadanou metodu profilování.  
  
## <a name="exclusive-options"></a>Vylučující možnosti  
 **Pro automatické označování** možnost lze použít pouze s **WinCounter** možnost.  
  
 **Pro automatické označování:** `Milliseconds`  
 Určuje počet milisekund, po mezi shromažďování dat čítačů výkonu systému Windows.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu nejsou zadány dvě čítačů výkonu systému Windows mají být vybrány v intervalu 1 000 milisekund.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)