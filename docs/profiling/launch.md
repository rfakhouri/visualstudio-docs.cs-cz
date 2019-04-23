---
title: Spuštění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c105f5176948271c832330f01d0d03d270e69a97
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110554"
---
# <a name="launch"></a>Spuštění
**Spuštění** možnost spuštění pomocí metody vzorkování profileru a také začne zadané aplikace.

 Použít **spuštění** možnost, je nutné zadat **ukázka** metoda ve **Start** možnost.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Launch:AppName [Options]
```

#### <a name="parameters"></a>Parametry
 `AppName` Název aplikace spustit. Úplné a částečné cesty z aktuálního adresáře. jsou podporovány.

## <a name="valid-options"></a>Platné možnosti
 Následující možnosti VSPerfCmd je možné kombinovat s **spuštění** možnost v jednom příkazovém řádku.

 **Spusťte:** `Method` Inicializuje relaci příkazového řádku profileru a nastaví zadané metodě profilování.

 **GlobalOn** a **GlobalOff** obnoví (**GlobalOn**) nebo pozastavení (**GlobalOff**) profilace, ale nemá na konci relace profilování.

 **ProcessOn:** `PID` a **ProcessOff**:`PID` Obnoví (**ProcessOn**) nebo pozastavení (**ProcessOff**) profilace pro zadaný proces.

 **TargetCLR** určuje verze nástroje rozhraní .NET Framework CLR Common Language Runtime () do profilu, když více než jedna verze je načten do relace profilování. Ve výchozím nastavení je Profilovat první načtené verze.

## <a name="exclusive-options"></a>Výhradní možnosti
 Tyto možnosti lze použít pouze s **spuštění** možnost.

 **Konzola** spustí zadaný aplikace příkazového řádku v novém okně.

 **Argumenty:** `ArgList` Určuje seznam argumentů pro předání do aplikace.

 **LineOff** zakazuje shromažďování dat profilování úrovně řádku.

## <a name="sampling-options"></a>Možnosti vzorkování
 Na lze zadat jedno z následujících možností interval vzorkování **spuštění** příkazového řádku. Výchozí interval vzorkování je 10 000 000 hodinových cyklů procesoru.

 **Časovač**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`] **Čítač**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**přidělení** &#124;  **Doba života**] Určuje počet a typ intervalu vzorkování.

- **Časovač** – ukázky každý `Cycles` procesoru nepřerušených hodinových cyklů. Pokud `Cycles` není zadán, 10 000 000 cykly se používají.

- **PF** – ukázky každý `Events` chyby stránek. Pokud `Events` není zadán, 10 chyby stránek.

- **Sys** – ukázky každý `Events` volání do operačního systému. Pokud `Events` není zadán, 10 volání systému se používají.

- **Čítač** – ukázky každý `Reload` počet výkon procesoru čítač určené `Name`. Volitelně můžete `FriendlyName` můžete zadejte řetězec, který se použije jako záhlaví sloupce v sestavy profileru.

- **Uvolňování paměti** – data paměti .NET shromažďuje. Ve výchozím nastavení (**přidělení**), data se shromažďují v každé události přidělení paměti. Když **životnost** parametr zadán, data se shromažďují také na všechny události uvolňování paměti kolekce.

## <a name="example"></a>Příklad
 Tento příklad ukazuje použití **spuštění** ke spuštění aplikace.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)