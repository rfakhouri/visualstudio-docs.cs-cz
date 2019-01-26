---
title: Odpojit | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ad079afe3202f7261f8de60d0616df57715e6717
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54919054"
---
# <a name="detach"></a>Odpojit
VSPerfCmd.exe **odpojit** možnost odpojí profiler z konkrétních procesů nebo všechny procesy, pokud nejsou zadány žádné. Profilace musí byly inicializovány pomocí metody vzorkování.  
  
 Profilace, který byl spuštěn s buď **spuštění** nebo **připojit** možnosti můžete odpojit s **odpojit**. Profiler může být reattched pomocí dalších **připojit** příkazy.  
  
 **Odpojit** nezavře soubor dat profilování. Použití **vypnutí** možnost ukončení profilace a uzavře soubor dat.  
  
> [!NOTE]
>  Pokud **Start** s byl zadán příkaz **Crosssession** možnost, všechna volání do **VSPerfCmd /Attach** nebo **VSPerfCmd/Detach** musí také zadejte **Crosssession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
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
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
;REM Excercise the application  
VSPerfCmd.exe /Detach  
VSPerfCmd.exe /Shutdown  
```  
  
## <a name="see-also"></a>Viz také:  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)