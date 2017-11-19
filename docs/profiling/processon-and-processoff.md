---
title: ProcessOn a ProcessOff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3dc6a7e-bc0f-48a6-a4ec-f386348bb296
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e187498656f1fd781d26e6b04426621bd2f3c3c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="processon-and-processoff"></a>ProcessOn a ProcessOff
VSPerfCmd.exe **ProcessOff** a **ProcessOn** dílčích příkazů pozastavení a obnovení profilace pro proces zadaný v profilaci relaci příkazového řádku. **ProcessOff** zastaví profilace proces a **ProcessOn** spustí profilace proces.  
  
 Ve většině případů zadáte **ProcessOn** nebo **ProcessOff** jako jedinou možností v VSPerfCmd.exe příkazového řádku, ale je také možné kombinovat s **GlobalOn**, **GlobalOff**, **ThreadOn**, a **ThreadOff** dílčích příkazů.  
  
 **ProcessOn** a **ProcessOff** dílčích příkazů interakci s **GlobalOn** a **GlobalOff** dílčích příkazů, které řídí dat kolekce pro všechny procesy v relaci příkazového řádku profilování a **ThreadOn** a **ThreadOff** dílčích příkazů, které řídí shromažďování dat pro zadaný vlákna.  
  
 **ProcessOff** a **ProcessOn** dílčích příkazů ovlivní také počet spuštění a zastavení procesu, který je zpracováván profileru rozhraní API funkce.  
  
-   **ProcessOff** okamžitě nastaví počet spuštění a zastavení procesu na 0 a proto pozastaví profilace.  
  
-   **ProcessOn** okamžitě nastaví počet spuštění a zastavení procesu na 1 a proto obnoví profilace.  
  
 Další informace najdete v tématu [profilace rozhraní API nástroje](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /{ProcessOff|ProcessOn}:PID [Options]  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `PID`  
 Celé číslo identifikátor procesu spuštění nebo zastavení. ID procesu jsou uvedeny na kartě proces Správce úloh systému Windows.  
  
## <a name="required-subcommands"></a>Požadované dílčích příkazů  
 Žádné  
  
## <a name="valid-subcommands"></a>Platný dílčích příkazů  
 **ProcessOn** a **ProcessOff** můžete nastavit na příkazových řádků, které také obsahují následující dílčích příkazů.  
  
 **Začátek:**`Method`  
 Inicializuje příkazového řádku relace profilování a nastaví zadanou metodu profilování.  
  
 **Spuštění:**`AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody vzorkování.  
  
 **Připojení:**`PID`  
 Zahájí profilace určený proces.  
  
 **GlobalOff**&#124; **GlobalOn**  
 Zastavení nebo spuštění profilace pro všechny procesy v profilaci relaci příkazového řádku.  
  
 {**ThreadOff**&#124; **ThreadOn**}**:**`TID`  
 Zastavení nebo spuštění profilace pro zadaný vlákno (pouze metody instrumentace).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **ProcessOff** podpříkaz se používá ke shromažďování dat profilace pro spuštění aplikace.  
  
```  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the process after startup.  
VSPerfCmd.exe /ProcessOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)