---
title: PF | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: cdc0a094-a986-4629-bd1c-dd5fdca323dc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf6bc8ae841ad8ba0d3fd376176bdff2332fb958
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431994"
---
# <a name="pf"></a>PF
*VSPerfCmd.exe* **PF** parametr nastaví profilování událost, která vede na chyby stránek a volitelně změní počet chyb stránek v intervalu vzorkování z výchozí hodnoty 10.

> [!NOTE]
> **PF** nelze použít v 64bitových systémech.

**PF** jde použít jenom v příkazovém řádku, který také obsahuje **spuštění** nebo **připojit** možnost.

 Ve výchozím nastavení je nastavena událost odběru vzorků na procesoru nepřerušených hodinových cyklů a interval vzorkování je nastavený na 10 000 000. **Časovače**, **PF**, **Sys**, a **čítač** možnosti umožňují nastavit interval vzorkování událostí a vzorkování. **GC** možnost shromažďuje data paměti .NET v každé události přidělování a uvolňování paměti kolekce. Na příkazovém řádku lze zadat pouze jeden z těchto možností.

 Událost odběru vzorků a interval vzorkování je možné nastavit pouze v první příkazového řádku, který obsahuje **spuštění** nebo **připojit** možnost.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /PF[:Events] [Options]
```

#### <a name="parameters"></a>Parametry
 `Events` Celočíselná hodnota, která určuje počet událostí selhání stránky v intervalu vzorkování. Pokud `Events` není zadán, je nastavit interval na 10.

## <a name="required-options"></a>Požadované možnosti
 **PF** lze zadat pouze na příkazovém řádku, který obsahuje jeden z následujících možností.

 **Spuštění:** `AppName` Spuštění profileru a aplikace určené AppName.

 **Připojení:** `PID` Připojí profiler k procesu určené AppName.

## <a name="invalid-options"></a>Neplatné možnosti
 Tyto možnosti nelze zadat na stejném příkazovém řádku jako **PF**.

 **Časovač**[ **:** `Cycles`] Nastaví událost odběru vzorků na hodin procesoru cykly a volitelně nastaví interval vzorkování na `Cycles`. Výchozí interval časovače je 10 000 000.

 **Sys**[ **:** `Events`] Nastaví událost odběru vzorků na volání od profilované aplikace do jádra operačního systému (syscalls) a případně nastaví interval vzorkování na `Events`. Výchozí Sys interval je 10.

 **Čítač:** `Name`[`,Reload`[`,FriendlyName`]] Nastaví událost odběru vzorků na výkon procesoru čítač určené `Name` a nastaví interval vzorkování na `Reload`.

 **Uvolňování paměti**[ **:** {**přidělení**&#124;**životnost**}] data paměti .NET shromažďuje. Ve výchozím nastavení (**přidělení**), data se shromažďují v každé události přidělení paměti. Když **životnost** parametr zadán, data se shromažďují také na všechny události uvolňování paměti kolekce.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak nastavit profilování událost vzorku pro chyby stránky a nastavit interval vzorkování na chyby 20 stránek.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /PF:20
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)