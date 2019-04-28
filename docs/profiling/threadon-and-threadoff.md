---
title: ThreadOn a ThreadOff | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5cd5a695-0a14-484a-8952-ed47e13d8e92
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2516ff5597151e65276b0fcb2bef5bb81c929cd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62965229"
---
# <a name="threadon-and-threadoff"></a>ThreadOn a ThreadOff
*VSPerfCmd.exe* **ThreadOff** a **ThreadOn** dílčí příkazy jsou dostupné jenom v příkazového řádku relace profilování, které používají metodu instrumentace. **ThreadOff** a **ThreadOn** pozastavit a obnovit profilace pro zadaný podproces. **ThreadOff** zastaví profilování vlákna a **ThreadOn** spuštění profilace vlákna.

 Ve většině případů je zadat **ThreadOn** nebo **ThreadOff** jako jedinou možností v *VSPerfCmd.exe* příkazového řádku, ale můžete také kombinovat s  **GlobalOn**, **GlobalOff**, **ProcessOn**, a **ProcessOff** dílčí příkazy.

 **ThreadOn** a **ThreadOff** dílčí příkazy pracovat **GlobalOn** a **GlobalOff** dílčí příkazy, které řídí dat kolekce pro všechny procesy v relaci příkazového řádku profilování a **ProcessOn** a **ProcessOff** dílčí příkazy, které řídí shromažďování dat pro zadaný proces.

 **ThreadOff** a **ThreadOn** dílčí příkazy také ovlivnit počet spuštění/zastavení vlákna, který je zpracováván pomocí funkcí profilování rozhraní API.

- **ThreadOff** okamžitě počet operací spustit/zastavit vlákna nastaví na hodnotu 0 a proto pozastaví profilace.

- **ThreadOn** okamžitě počet operací spustit/zastavit vlákna nastaví na 1 a proto obnoví profilace.

  Další informace najdete v tématu [nástroje rozhraní API pro profilaci](../profiling/profiling-tools-apis.md).

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /{ThreadOff|ThreadOn}:TID [Options]

```

#### <a name="parameters"></a>Parametry
 `TID` Celé číslo identifikátor vlákna spuštění nebo zastavení.

## <a name="valid-options"></a>Platné možnosti
 **ThreadOn** a **ThreadOff** se dá nastavit na příkazové řádky, které také obsahují následující dílčí příkazy.

 **Spusťte:** `Method` Inicializuje relaci příkazového řádku profilování a nastaví zadané metodě profilování.

 **GlobalOff**&#124;**GlobalOn** zastavení nebo spuštění profilace pro všechny procesy v relaci příkazového řádku profilování.

 {**ProcessOff**&#124;**ProcessOn**}**:**`TID` Zastavení nebo spuštění profilace pro zadaný proces.

## <a name="example"></a>Příklad
 V tomto příkladu **ThreadOff** podpříkaz slouží k zastavení shromažďování dat profilování tak, aby se shromažďují pouze data po spuštění aplikace.

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
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)