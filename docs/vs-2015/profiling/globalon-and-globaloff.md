---
title: GlobalOn a GlobalOff | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b0ed68-d19e-473e-9af3-252c11d82bcf
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9d80ff0f0e7177c95eb7d1c4607004bf7f70b7a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671238"
---
# <a name="globalon-and-globaloff"></a>GlobalOn a GlobalOff
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [GlobalOn a GlobalOff](https://docs.microsoft.com/visualstudio/profiling/globalon-and-globaloff).  
  
VSPerfCmd.exe **GlobalOff** a **GlobalOn** možnosti pozastavení a pokračování v relaci profilace příkazového řádku pro profilaci pro všechny procesy a vlákna.  
  
 Můžete zadat **GlobalOn** a **GlobalOff** pouze možnosti VSPerfCmd.exe příkazového řádku, nebo může obsahovat na příkazových řádcích, které také obsahují **Start**, **Spuštění**, nebo **připojit** možnosti.  
  
 **GlobalOn** a **GlobalOff** se dají kombinovat taky s **ProcessOn**, **ProcessOff**, **ThreadOn**a  **ThreadOff** možnosti.  
  
 **GlobalOn** a **GlobalOff** možnosti pracovat **ProcessOn** a **ProcessOff** možnosti, které řídí shromažďování dat pro Zadaný proces a **ThreadOn** a **ThreadOff** možnosti, které řídí shromažďování dat pro zadaný podproces.  
  
 **GlobalOff** a **GlobalOn** možnosti také ovlivnit počet globální spuštění/zastavení, který je zpracováván funkcí rozhraní API profileru.  
  
-   **GlobalOff** okamžitě Nastaví globální počet operací spustit/zastavit na hodnotu 0 a proto pozastaví profilace.  
  
-   **GlobalOn** okamžitě Nastaví globální počet operací spustit/zastavit na hodnotu 1 a proto obnoví profilace.  
  
 Další informace najdete v tématu [profilování rozhraní API nástroje](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /{GlobalOff|GlobalOn}  
  
VSPerfCmd.exe /Start:Method /{GlobalOff|GlobalOn} [Options]  
  
VSPerfCmd.exe {Launch:AppName|Attach:PID} /{GlobalOff|GlobalOn}[Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="valid-options"></a>Platné možnosti  
 **GlobalOn** a **GlobalOff** se dá nastavit na příkazové řádky, které také obsahují následující možnosti.  
  
 **Spusťte:** `Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadané metodě profilování.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.  
  
 **Připojení:** `PID`  
 Zahájení profilace určeného procesu.  
  
 {**ProcessOff**&#124;**ProcessOn**}**:**`PID`  
 Zastavení nebo spuštění profilace pro zadaný proces.  
  
 {**ThreadOff**&#124;**ThreadOn**}**:**`TID`  
 Zastavení nebo spuštění profilace pro zadaný proces (pouze metody instrumentace).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **GlobalOff** a **GlobalOn** možnosti slouží k zamezení shromažďování profilovacích dat pro spuštění aplikace a vypnutí.  
  
```  
; Initialize the profiler with profiling stopped.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp /GlobalOff  
; Start an instrumented application and wait for it to warm up.  
; Start profiling.  
VSPerfCmd.exe /GlobalOn  
; Exercise the application functionality that you want to profile.  
; Stop profiling.  
VSPerfCmd.exe /GlobalOff  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)



