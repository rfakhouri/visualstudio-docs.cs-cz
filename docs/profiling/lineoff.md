---
title: LineOff | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b4de8aa278adab0127f3a39d9adcf105f906e152
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62995328"
---
# <a name="lineoff"></a>LineOff
Ve výchozím nastavení profiler shromažďuje zdrojového kódu řádek číslo a řádek číslo posunu data při použití metoda profilování vzorkování. Příkazu vsperfcmd proveďte **LineOff** možnost zakazuje shromažďování dat číslo řádku, když, VSPerfCmd se používá ke spuštění aplikace. Funkce jsou shromažďována data profilování úrovni v případě **LineOff** určena.

 Můžete použít **LineOff** pouze s **spuštění** možnost, a pouze pokud profiler byl inicializován pro vzorkování pomocí **Start**:**ukázka** možnost.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Launch:AppName /LineOff [Options]
```

#### <a name="parameters"></a>Parametry
 Žádný

## <a name="required-options"></a>Požadované možnosti
 **LineOff** možnost použít jenom na příkazovém řádku, který obsahuje **spuštění** možnost.

 **Spuštění:** `AppName` Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.

## <a name="example"></a>Příklad
 Tento příklad spustí aplikaci a profiler a zakáže vzorkování na úrovni řádku.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /LineOff
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)