---
title: WinCounter | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9a8e381ed058c30dcbf1760f380cf065c1443cd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669804"
---
# <a name="wincounter"></a>WinCounter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [WinCounter](https://docs.microsoft.com/visualstudio/profiling/wincounter).  
  
**WinCounter** určuje Windows nebo čítač výkonu aplikace na shromažďování v nastavených intervalech během profil spustit. Windows a čítače výkonu aplikace jsou uvedené jako značky v souboru dat profilování. Můžete zadat více čítačů výkonu k získání v samostatné možnosti.  
  
 Ve výchozím nastavení, se shromažďují čítače každých 500 milisekund. Použití **AutoMark** lze zadat interval jinou kolekci.  
  
 Pouze jeden **AutoMark** možnost se používá. Pokud je položek víc **AutoMark** možnosti se uvádějí, použije se ten poslední.  
  
 **WinCounter** možnost se dá použít jenom s **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)



