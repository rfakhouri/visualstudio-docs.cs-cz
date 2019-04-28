---
title: Využití procesoru měření z příkazového řádku
description: Měření výkonu procesoru v aplikaci z příkazového řádku.
ms.custom: ''
ms.date: 02/19/2019
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, command-line
- Diagnostics Tools, command-line
- CPU Usage, command-line
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.workload:
- multiple
ms.openlocfilehash: 87bf0c236f34e753866ea114dfc7f45e8f16a979
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62972412"
---
# <a name="measure-application-performance-from-the-command-line"></a>Měřit výkon aplikace z příkazového řádku

Shromažďování informací o aplikaci pomocí nástrojů příkazového řádku.

V příkladu popisovaného v tomto článku můžete shromažďovat informace o výkonu pro Microsoft Notepad, ale stejnou metodu je možné profilovat nějaký proces.

## <a name="prerequisites"></a>Požadavky

* Visual Studio. 2019 ve verzi Preview 3 nebo novější verze

* Seznámení se s nástroji příkazového řádku

## <a name="collect-performance-data"></a>Shromažďování dat výkonu

Profilace s použitím nástroje rozhraní příkazového řádku Diagnostika Visual Studio funguje tak, že připojení k procesu nástroje pro profilaci, společně s jednou z agentů shromažďování. Při připojení nástroje pro profilaci, zahájit relaci diagnostiky shromažďuje a ukládá data profilování, dokud nebude zastaven nástroj, kdy se tato data exportuje do *.diagsession* souboru. Tento soubor pak můžete otevřít ve Visual Studiu a analyzujte výsledky.

1. Spusťte program Poznámkový blok a pak otevřete Správce úloh zobrazíte jeho ID procesu (PID). PID v najít ve Správci úloh **podrobnosti** kartu.

1. Otevřete příkazový řádek a přejděte do adresáře s agentem kolekce spustitelný soubor, obvykle tady.

   ```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\```

1. Spustit *VSDiagnostics.exe* tak, že zadáte následující příkaz.

   ```cmd
   VSDiagnostics.exe start <id> /attach:<pid> /loadConfig:<configFile>
   ```

   Argumenty, které musí být zahrnuty jsou následující:

   * \<*ID*> identifikuje relace shromažďování. ID musí být číslo mezi 1-255.
   * \<*Identifikátor PID*>, PID procesu, kterou chcete profil, v tomto případě identifikátor PID jste získali v kroku 1
   * \<*configFile*>, konfigurační soubor pro agenta shromažďování chcete spustit. Další informace najdete v tématu [konfigurační soubory pro agenty](#config_file).

1. Změna velikosti Poznámkový blok nebo pokud chcete mít jistotu, že některé zajímavé profilování informace jsou shromažďovány něco zadejte do něj.

1. Zastavit relaci shromažďování a posílat výstup do souboru tak, že zadáte následující příkaz.

   ```cmd
   VSDiagnostics.exe stop <id> /output:<path to file>
   ```

1. Přejděte do souboru výstupu z předchozího příkazu a otevřete ho v sadě Visual Studio k prozkoumání shromážděné informace.

## <a name="config_file"></a> Konfigurační soubory agenta

Kolekce agenti jsou zaměnitelné komponenty, která shromažďují různé typy dat v závislosti na tom, co se pokoušíte měření.

Pro usnadnění práce můžete uložit tyto informace v konfiguračním souboru agenta. Konfigurační soubor je *.json* soubor, který obsahuje název aspoň *.dll* a jeho identifikátor CLSID modelu COM. Tady je příklad konfigurační soubory, které najdete v následující složce:

```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\AgentConfigs\```

* Konfigurace CpuUsage (základní nebo vysoká nebo nízká), které odpovídá dat shromážděných pro [využití procesoru](../profiling/cpu-usage.md) nástroje pro profilaci.
* Konfigurace DotNetObjectAlloc (základní nebo nízká), které odpovídá dat shromážděných pro [nástroj přidělování objektů .NET](https://devblogs.microsoft.com/visualstudio/visual-studio-2017-version-15-8-preview-3/#tooling).

Konfigurace Base/nízká/vysoká najdete vzorkovací frekvenci. Například Nízká je 100 vzorků za sekundu a vyšší je 4000 vzorků za sekundu.

Pro *VSDiagnostics.exe* nástroj pro práci s agentem kolekce, vyžaduje knihovny DLL a identifikátor CLSID modelu COM pro odpovídajícího agenta a agent může mít také možnosti další konfigurace. Pokud používáte agenta bez konfiguračního souboru, použijte formát v následujícím příkazu.

```cmd
VSDiagnostics.exe start <id> /attach:<pid> /loadAgent:<agentCLSID>;<agentName>[;<config>]
```

## <a name="permissions"></a>Oprávnění

Chcete-li Profilovat aplikaci, která vyžaduje zvýšenou úroveň oprávnění, musíte tak učinit z příkazového řádku se zvýšenými oprávněními.
