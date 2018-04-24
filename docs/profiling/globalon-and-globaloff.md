---
title: GlobalOn a GlobalOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 24b0ed68-d19e-473e-9af3-252c11d82bcf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3009130acbbde431c9751df848eaef252c0bdd04
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
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
  
 **Spusťte:** `Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadanou metodu profilování.  
  
 **Spusťte:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
 **Připojení:** `PID`  
 Zahájí profilace určený proces.  
  
 {**ProcessOff**&#124;**ProcessOn**}**:**`PID`  
 Zastavení nebo spuštění profilace pro proces zadaný.  
  
 {**ThreadOff**&#124;**ThreadOn**}**:**`TID`  
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