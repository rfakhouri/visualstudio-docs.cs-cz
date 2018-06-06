---
title: ThreadOn a ThreadOff | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5cd5a695-0a14-484a-8952-ed47e13d8e92
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9ef0bfc6c2030fc12d5743e91cb7b660cbe241f
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34476674"
---
# <a name="threadon-and-threadoff"></a>ThreadOn a ThreadOff
VSPerfCmd.exe **ThreadOff** a **ThreadOn** dílčích příkazů jsou dostupné jenom v příkazového řádku profilování relace, které používají metody instrumentace. **ThreadOff** a **ThreadOn** pozastavení a obnovení profilace pro zadaný vlákno. **ThreadOff** zastaví profilace vlákno a **ThreadOn** spustí profilace vlákno.  
  
 Ve většině případů zadáte **ThreadOn** nebo **ThreadOff** jako jedinou možností v VSPerfCmd.exe příkazového řádku, ale je také možné kombinovat s **GlobalOn**, **GlobalOff**, **ProcessOn**, a **ProcessOff** dílčích příkazů.  
  
 **ThreadOn** a **ThreadOff** dílčích příkazů interakci s **GlobalOn** a **GlobalOff** dílčích příkazů, které řídí dat kolekce pro všechny procesy v relaci příkazového řádku profilování a **ProcessOn** a **ProcessOff** dílčích příkazů, které řídí shromažďování dat pro zadaný procesu.  
  
 **ThreadOff** a **ThreadOn** dílčích příkazů ovlivní také počet vláken spuštění a zastavení, který je zpracováván profileru rozhraní API funkce.  
  
-   **ThreadOff** okamžitě nastaví spuštění a zastavení počtu vláken na 0 a proto pozastaví profilace.  
  
-   **ThreadOn** okamžitě nastaví spuštění a zastavení počet vláken na 1 a proto obnoví profilace.  
  
 Další informace najdete v tématu [rozhraní API nástrojů pro profil](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /{ThreadOff|ThreadOn}:TID [Options]  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `TID`  
 Identifikátor celé číslo vlákna na spuštění nebo zastavení.  
  
## <a name="valid-options"></a>Platné možnosti.  
 **ThreadOn** a **ThreadOff** můžete nastavit na příkazových řádků, které také obsahují následující dílčích příkazů.  
  
 **Spusťte:** `Method`  
 Inicializuje příkazového řádku relace profilování a nastaví zadanou metodu profilování.  
  
 **GlobalOff**&#124;**GlobalOn**  
 Zastavení nebo spuštění profilace pro všechny procesy v profilaci relaci příkazového řádku.  
  
 {**ProcessOff**&#124;**ProcessOn**}**:**`TID`  
 Zastavení nebo spuštění profilace pro proces zadaný.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu **ThreadOff** podpříkaz se používá k ukončení shromažďování data profilování tak, aby se shromažďují jenom data po spuštění aplikace.  
  
```cmd  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the thread after startup.  
VSPerfCmd.exe /ThreadOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Viz také:  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profil samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)