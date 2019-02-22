---
title: ProcessOn a ProcessOff | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d3dc6a7e-bc0f-48a6-a4ec-f386348bb296
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab218f8dabb2b4360c1be17d809399a752f7cc2c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611799"
---
# <a name="processon-and-processoff"></a>ProcessOn a ProcessOff
VSPerfCmd.exe **ProcessOff** a **ProcessOn** dílčí příkazy pozastavit a pokračovat v Profilování pro zadaný proces v relaci příkazového řádku profilování. **ProcessOff** zastaví profilování procesu a **ProcessOn** spustí profilaci procesu.

 Ve většině případů je zadat **ProcessOn** nebo **ProcessOff** jako jedinou možností v VSPerfCmd.exe příkazového řádku, ale můžete také kombinovat s **GlobalOn**, **GlobalOff**, **ThreadOn**, a **ThreadOff** dílčí příkazy.

 **ProcessOn** a **ProcessOff** dílčí příkazy pracovat **GlobalOn** a **GlobalOff** dílčí příkazy, které řídí dat kolekce pro všechny procesy v relaci příkazového řádku profilování a **ThreadOn** a **ThreadOff** dílčí příkazy, které řídí shromažďování dat pro zadaný podproces.

 **ProcessOff** a **ProcessOn** dílčí příkazy také ovlivnit počet spuštění/zastavení procesu, který je zpracováván pomocí funkcí profilování rozhraní API.

- **ProcessOff** okamžitě nastaví počet operací spustit/zastavit proces na hodnotu 0 a proto pozastaví profilace.

- **ProcessOn** okamžitě nastaví počet operací spustit/zastavit proces na 1 a proto obnoví profilace.

  Další informace najdete v tématu [profilování rozhraní API nástroje](../profiling/profiling-tools-apis.md).

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /{ProcessOff|ProcessOn}:PID [Options]

```

#### <a name="parameters"></a>Parametry
 `PID` Celé číslo identifikátor procesu spuštění nebo zastavení. ID procesu jsou uvedeny na **procesu** karty ve Správci úloh Windows.

## <a name="required-subcommands"></a>Požadovaný dílčí příkazy
 Žádná

## <a name="valid-subcommands"></a>Neplatný dílčí příkazy
 **ProcessOn** a **ProcessOff** se dá nastavit na příkazové řádky, které také obsahují následující dílčí příkazy.

 **Spusťte:** `Method` Inicializuje relaci příkazového řádku profilování a nastaví zadané metodě profilování.

 **Spuštění:** `AppName` Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.

 **Připojení:** `PID` Zahájení profilace určeného procesu.

 **GlobalOff**&#124;**GlobalOn** zastavení nebo spuštění profilace pro všechny procesy v relaci příkazového řádku profilování.

 {**ThreadOff**&#124;**ThreadOn**}**:**`TID` Zastavení nebo spuštění profilování pro zadaný podproces (pouze metody instrumentace).

## <a name="example"></a>Příklad
 V tomto příkladu **ProcessOff** podpříkaz se používá ke shromažďování dat profilování pro spuštění aplikace.

```cmd
; Initialize the profiler.
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp
; Start the instrumented application.
; Stop profiling the process after startup.
VSPerfCmd.exe /ProcessOff:12345
; Shut down the target application.
; Close the profiler.
VSPerfCmd /Shutdown

```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)