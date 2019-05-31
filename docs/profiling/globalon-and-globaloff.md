---
title: GlobalOn a GlobalOff | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 24b0ed68-d19e-473e-9af3-252c11d82bcf
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2ee29b677096e46d965e8191cf26a829587471dd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969625"
---
# <a name="globalon-and-globaloff"></a>GlobalOn a GlobalOff
*VSPerfCmd.exe* **GlobalOff** a **GlobalOn** možnosti pozastavení a pokračování profilování pro všechny procesy a vlákna v relaci příkazového řádku profilování.

 Můžete zadat **GlobalOn** a **GlobalOff** jako možnosti pouze *VSPerfCmd.exe* příkazového řádku, nebo můžete zahrnout do příkazové řádky, které obsahují také  **Start**, **spuštění**, nebo **připojit** možnosti.

 **GlobalOn** a **GlobalOff** se dají kombinovat taky s **ProcessOn**, **ProcessOff**, **ThreadOn**a  **ThreadOff** možnosti.

 **GlobalOn** a **GlobalOff** možnosti pracovat **ProcessOn** a **ProcessOff** možnosti, které řídí shromažďování dat pro Zadaný proces a **ThreadOn** a **ThreadOff** možnosti, které řídí shromažďování dat pro zadaný podproces.

 **GlobalOff** a **GlobalOn** možnosti také ovlivnit počet globální spuštění/zastavení, který je zpracováván funkcí rozhraní API profileru.

- **GlobalOff** okamžitě Nastaví globální počet operací spustit/zastavit na hodnotu 0 a proto pozastaví profilace.

- **GlobalOn** okamžitě Nastaví globální počet operací spustit/zastavit na hodnotu 1 a proto obnoví profilace.

  Další informace najdete v tématu [nástroje rozhraní API pro profilaci](../profiling/profiling-tools-apis.md).

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /{GlobalOff|GlobalOn}

VSPerfCmd.exe /Start:Method /{GlobalOff|GlobalOn} [Options]

VSPerfCmd.exe {Launch:AppName|Attach:PID} /{GlobalOff|GlobalOn}[Options]
```

#### <a name="parameters"></a>Parametry
 Žádné

## <a name="valid-options"></a>Platné možnosti
 **GlobalOn** a **GlobalOff** se dá nastavit na příkazové řádky, které také obsahují následující možnosti.

 **Spusťte:** `Method` Inicializuje relaci příkazového řádku profileru a nastaví zadané metodě profilování.

 **Spuštění:** `AppName` Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.

 **Připojení:** `PID` Zahájení profilace určeného procesu.

 {**ProcessOff**&#124;**ProcessOn**} **:** `PID` Zastavení nebo spuštění profilace pro zadaný proces.

 {**ThreadOff**&#124;**ThreadOn**} **:** `TID` Zastavení nebo spuštění profilace pro zadaný proces (pouze metody instrumentace).

## <a name="example"></a>Příklad
 V tomto příkladu **GlobalOff** a **GlobalOn** možnosti slouží k zamezení shromažďování profilovacích dat pro spuštění aplikace a vypnutí.

```cmd
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

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)