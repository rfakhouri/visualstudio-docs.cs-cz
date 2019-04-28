---
title: Připojit | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 79614283-6733-4592-a53a-d428052271ad
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f080957774b33ca00787f061708426a62bd7768f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440298"
---
# <a name="attach"></a>Připojit
*VSPerfCmd.exe* **připojit** možnost zahájení profilace vzorku spuštěný proces zadaný pomocí ID procesu (PID).

 Použít **připojit** možnost, je nutné zadat **ukázka** metoda ve variantě pro spuštění.

> [!NOTE]
> Pokud **Start** s byl zadán příkaz **Crosssession** možnost, všechna volání do **VSPerfCmd /Attach** nebo **VSPerfCmd/Detach** musí také zadejte **Crosssession**.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Attach:ProcessID [Options]
```

#### <a name="parameters"></a>Parametry
 `ProcessID` ID procesu (PID) spuštěného procesu. Na kartě procesy ve Správci úloh Windows je uvedena PID spuštěnému procesu.

## <a name="valid-options"></a>Platné možnosti
 Následující **VSPerfCmd** možnosti lze kombinovat s **připojit** možnost v jednom příkazovém řádku.

 **Crosssession** umožňuje profilování aplikace v relacích než přihlašovací relace. Požadováno pokud **Start** s byl zadán příkaz **Crosssession** možnost.

 **Spusťte:** `Method` Inicializuje relaci příkazového řádku profileru a nastaví zadané metodě profilování.

 **TargetCLR** určuje verze nástroje rozhraní .NET Framework CLR Common Language Runtime () do profilu, když více než jedna verze je načten do relace profilování. Ve výchozím nastavení je Profilovat první načtené verze.

 **GlobalOn GlobalOff** obnoví (**GlobalOn**) nebo pozastavení (**GlobalOff**) profilace, ale nemá na konci relace profilování.

 **ProcessOn:** `PID` **ProcessOff:** `PID` Obnoví (**ProcessOn**) nebo pozastavení (**ProcessOff**) profilace pro zadaný proces.

## <a name="interval-options"></a>Možnosti intervalu
 Jeden z následujících možností interval vzorkování se dá nastavit na příkazovém řádku připojit. Výchozí interval vzorkování je 10 000 000 hodinových cyklů procesoru.

 **Časovač**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[<strong>:</strong> Události]**čítač**[**:**`Name`,`Reload`,`FriendlyName`] Určuje počet a typ použitého intervalu vzorkování.

- **Časovač** – ukázky každý `Cycles` hodinových cyklů procesoru. Pokud `Cycles` není zadán, 10 000 000 cykly se používají.

- **PF** – ukázky každý `Events` chyby stránek. Pokud `Events` není zadán, 10 chyb stránky se používají.

- **Sys** – ukázky každý `Events` volání do operačního systému. Pokud `Events` není zadán, 10 volání systému se používají.

- **Čítač** – ukázky každý `Reload` počet výkon procesoru čítač určené `Name`. Volitelně můžete `FriendlyName` můžete zadejte řetězec, který se použije jako záhlaví sloupce v sestavy profileru.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak se připojit ke spuštěné instanci aplikace s ID procesu 12345.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Attach:12345
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)