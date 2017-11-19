---
title: GlobalOn a GlobalOff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b0ed68-d19e-473e-9af3-252c11d82bcf
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26a85326dec53adce4ac9c5b1bdedaca1e38beec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="globalon-and-globaloff"></a>GlobalOn a GlobalOff
VSPerfCmd.exe **GlobalOff** a **GlobalOn** možnosti pozastavení a obnovení profilace pro všechny procesy a vláken v profilaci relaci příkazového řádku.  
  
 Můžete zadat **GlobalOn** a **GlobalOff** jako pouze možnosti příkazového řádku VSPerfCmd.exe, nebo můžete zahrnout do příkazové řádky, které také obsahují **spustit**, **Spusťte**, nebo **Attach** možnosti.  
  
 **GlobalOn** a **GlobalOff** může být spojen s **ProcessOn**, **ProcessOff**, **ThreadOn**a  **ThreadOff** možnosti.  
  
 **GlobalOn** a **GlobalOff** možnosti interakci s **ProcessOn** a **ProcessOff** možnosti, které řídí shromažďování dat pro Zadaný procesu a **ThreadOn** a **ThreadOff** možnosti, které řídí shromažďování dat pro zadaný vlákna.  
  
 **GlobalOff** a **GlobalOn** možnosti ovlivní také globální spuštění a zastavení počet, který je zpracováván profileru funkce rozhraní API.  
  
-   **GlobalOff** okamžitě Nastaví globální počet spuštění a zastavení na 0 a proto pozastaví profilace.  
  
-   **GlobalOn** okamžitě Nastaví globální počet spuštění a zastavení na 1 a proto obnoví profilace.  
  
 Další informace najdete v tématu [profilace rozhraní API nástroje](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /{GlobalOff|GlobalOn}  
  
VSPerfCmd.exe /Start:Method /{GlobalOff|GlobalOn} [Options]  
  
VSPerfCmd.exe {Launch:AppName|Attach:PID} /{GlobalOff|GlobalOn}[Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="valid-options"></a>Platné možnosti.  
 **GlobalOn** a **GlobalOff** můžete nastavit na příkazových řádků, které také obsahují následující možnosti.  
  
 **Začátek:**`Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadanou metodu profilování.  
  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
 **Připojení:**`PID`  
 Zahájí profilace určený proces.  
  
 {**ProcessOff**&#124; **ProcessOn**}**:**`PID`  
 Zastavení nebo spuštění profilace pro proces zadaný.  
  
 {**ThreadOff**&#124; **ThreadOn**}**:**`TID`  
 Zastavení nebo spuštění profilace pro proces zadaný (pouze metody instrumentace).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **GlobalOff** a **GlobalOn** slouží k zamezení shromažďování data profilování pro spuštění aplikace a vypnutí.  
  
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
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)