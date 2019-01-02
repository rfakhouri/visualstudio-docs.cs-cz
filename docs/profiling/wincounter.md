---
title: WinCounter | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51cb5aa0a41f311ea9c24a4ed512d6df4fe2e10f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875216"
---
# <a name="wincounter"></a>WinCounter
**WinCounter** určuje Windows nebo čítač výkonu aplikace na shromažďování v nastavených intervalech během profil spustit. Windows a čítače výkonu aplikace jsou uvedené jako značky v souboru dat profilování. Můžete zadat více čítačů výkonu k získání v samostatné možnosti.  
  
 Ve výchozím nastavení, se shromažďují čítače každých 500 milisekund. Použití **AutoMark** lze zadat interval jinou kolekci.  
  
 Pouze jeden **AutoMark** možnost se používá. Pokud je položek víc **AutoMark** možnosti se uvádějí, použije se ten poslední.  
  
 **WinCounter** možnost se dá použít jenom s **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Path`  
 Čítače výkonu Windows ve formátu cesty čítače PDH.  
  
## <a name="required-options"></a>Požadované možnosti  
 **WinCounter** možnost se dá použít jenom s **Start** možnost.  
  
 **Spusťte:** `Method`  
 **Start** možnost inicializuje profiler k zadané metodě profilování.  
  
## <a name="exclusive-options"></a>Výhradní možnosti  
 **AutoMark** možnost se dá použít jenom s **WinCounter** možnost.  
  
 **AutoMark:** `Milliseconds`  
 Určuje počet milisekund mezi shromažďování dat čítačů výkonu Windows.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu jsou uvedeny dva čítače výkonu Windows se mají shromažďovat v intervalu 1 000 milisekund.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)