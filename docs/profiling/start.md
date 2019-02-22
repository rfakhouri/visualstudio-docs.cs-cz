---
title: Spuštění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df1e76c895102d5a33d66628a7c6436ab604b1ba
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639762"
---
# <a name="start"></a>Spustit
**Start** volba je *VSPerfCmd.exe* možnost, která inicializuje možnost profileru zadané metodě profilování.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName [Options]
```

#### <a name="parameters"></a>Parametry
 `Method` Musí být jedna z následujících klíčových slov:

-   **TRASOVÁNÍ** -určuje metody instrumentace.

-   **Ukázka** -určuje metody vzorkování.

-   **POKRYTÍ** -určuje pokrytí kódu.

-   **SOUBĚŽNOST** -určuje metodu kolize prostředků.

## <a name="required-options"></a>Požadované možnosti
 **Výstup** možnost musí být zadán při **Start** je zadán v příkazovém řádku.

 **Výstup:** `filename` Určuje název výstupního souboru.

## <a name="exclusive-options"></a>Výhradní možnosti
 Tyto možnosti lze použít pouze s **Start** možnost příkazového řádku.

 **CrossSession**&#124;**CS** umožňuje procesy profilace. Názvy možností **CrossSession** a **CS** jsou podporovány.

 **Uživatel:**[`domain\`]`username` umožňuje přístup klienta k monitoru ze zadaného účtu.

 **WinCounter:** `Path` [**Automark**:`n`] **WinCounter** určuje čítač výkonu Windows zahrnout jako značky v souboru dat profilování. **AutoMark** Určuje interval v milisekundách mezi kolekcemi datového souboru.

## <a name="invalid-options"></a>Neplatné možnosti
 Tyto možnosti nelze použít s **Start** možnost příkazového řádku.

 **Stav** **stav** se vztahuje na tyto procesy, které jsou profilovány. Vypíše procesy a vlákna a jejich aktuální stavy profilu (zapnuto/vypnuto). Například, pokud proces zastavená **stav** nebude to znamenat v sestavě. **Stav** se zobrazí, že je buď profilována procesu nebo ne.

 **Vypnutí**[**:**`Timeout`] profiler vypne.

## <a name="example"></a>Příklad
 Následující příklad ukazuje způsob použití *VSPerfCmd.exe* **Start** možnost pro inicializaci profileru.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)