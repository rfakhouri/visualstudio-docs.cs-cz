---
title: Odpojit | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56ad870d4638607ad03b60b33bb7d648dbbca424
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669096"
---
# <a name="detach"></a>Odpojit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [odpojit](https://docs.microsoft.com/visualstudio/profiling/detach).  
  
VSPerfCmd.exe **odpojit** možnost odpojí profiler z konkrétních procesů nebo všechny procesy, pokud žádný není zadaný. Profilace musí byly inicializovány pomocí metody vzorkování.  
  
 Profilace, který byl spuštěn s buď **spuštění** nebo **připojit** možnosti můžete odpojit s **odpojit**. Profiler může být reattched pomocí dalších **připojit** příkazy.  
  
 **Odpojit** nezavře soubor dat profilování. Použití **vypnutí** možnost ukončení profilace a uzavře soubor dat.  
  
> [!NOTE]
>  Pokud **Start** s byl zadán příkaz **Crosssession** možnost, všechna volání do **VSPerfCmd /Attach** nebo **VSPerfCmd/Detach** musí také zadejte **Crosssession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]  
```  
  
#### <a name="parameters"></a>Parametry  
 `PIDs|ProcessNames`  
 `PID` -Identifikátorem číselného systému jeden nebo více procesů.  
  
 `ProcessNames` -Název procesu. Pokud běží více instancí procesu pojmenované, jsou výsledky nepředvídatelné.  
  
 Více procesů oddělujte čárkami.  
  
 Pokud není zadán žádný proces, je profiler odpojen od všech profilovaných procesů.  
  
## <a name="valid-options"></a>Platné možnosti  
 Následující **VSPerfCmd** možnosti lze kombinovat s **připojit** možnost v jednom příkazovém řádku.  
  
 **Crosssession**  
 Umožňuje profilování aplikace v relacích než přihlašovací relace. Požadováno pokud **Start** s byl zadán příkaz **Crosssession** možnost.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **odpojit** příkaz pozastaví, profilace a **vypnutí** příkaz zavření souboru dat profilování.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)



