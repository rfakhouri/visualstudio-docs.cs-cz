---
title: Ladění kódu R
description: Visual Studio poskytuje úplné možnosti ladění pro R, včetně zarážek, připojit, volání zásobníku a zkontrolujete proměnné.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: 98dcbaaeb6f330cda3a14cf8c32afe403b50aa85
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62939266"
---
# <a name="debug-r-in-visual-studio"></a>Ladění jazyka R v sadě Visual Studio

Nástroje R pro Visual Studio (RTVS) integruje do úplného ladicího prostředí sady Visual Studio (viz [ladění v sadě Visual Studio](/visualstudio/debugger/debugger-feature-tour). Tato podpora zahrnuje zarážky, připojení ke spuštěným procesům, proměnné kontrolní a sledováním a zkontrolujete zásobníku volání. Tento článek se věnuje pak tyto aspekty ladění, které jsou jedinečné pro R a RTVS.

Spouští se ladicí program pro spouštěcí R soubor v projektu jazyka R je stejný jako u jiných typů projektů: použijte **ladění** > **spustit ladění**, **F5** klíč, nebo **Zdrojový soubor spouštěcí** na panelu nástrojů ladění:

![Ladicí program tlačítko start pro R](media/debugger-start-button.png)

Chcete-li změnit spouštěcí soubor, klikněte pravým tlačítkem na soubor v Průzkumníku řešení a vyberte **nastavit jako spouštěcí skript jazyka R**.

Ve všech případech se spuštění ladicího programu "zdroje" soubor v interaktivním okně, což znamená, že načtením a spouštět ho existuje, jak je znázorněno v interaktivním okně výstupu:

```output
> rtvs::debug_source("c:/proj/rproject1/rproject1/script.R")
Sourcing: c:\proj\rproject1\rproject1\script.R
Sourcing: c:\proj\rproject1\rproject1\Settings.R
```

Všimněte si, že `rtvs::debug_source` funkce se používá jako zdroj skript. Tato funkce se totiž RTVS je potřeba upravit kód v rámci přípravy pro ladění. Když je připojen pomocí libovolného příkazu zdrojové RTVS a ladicí program, Visual Studio automaticky použije `rtvs::debug_source`.

Můžete také ručně připojit ladicí program v interaktivním okně přímo pomocí **nástroje R** > **relace** > **připojit ladicí program** příkaz **ladění** > **připojit k interaktivní R** příkazu, nebo **připojit ladicí program** příkaz na interaktivní okno nástrojů. Jakmile to uděláte, je vaší odpovědností, abyste zdrojové soubory, které chcete ladit. Pokud chcete ručně zdrojové soubory, ujistěte se, že používáte `rtvs::debug_source` a není standardní `source` příkaz v jazyce R.

Toto připojení mezi ladicího programu a interaktivní okno je snazší provádět věci, jako je volání (a ladění) funkce s různými hodnotami parametrů. Předpokládejme například, že máte následující funkci v souboru source (tj. je načten do relace):

```R
add <- function(x, y) {
    return(x + y)
}
```

Nastavit zarážku na `return` příkazu. Teď v interaktivním okně zadáte `add(4,5)` ladicí program se zastaví na zarážku.

## <a name="environment-browser-in-the-interactive-window"></a>Prohlížeče prostředí v interaktivním okně

Po zastavení v ladicím programu můžete také zastavit na příkazový řádek prohlížeče prostředí v [interaktivní okno](interactive-repl-for-r-in-visual-studio.md). Zobrazení výzvy se zobrazí jako `Browse[n]>` kde n je číslo.

Prohlížeč prostředí podporuje řadu příkazů, speciální:

| Příkaz | Popis |
| --- | --- |
| n | Další: spustí další příkaz v kódu souboru (stejně jako krok přes). |
| s | Krok dovnitř: spustí další příkaz v souboru kódu, krokování s vnořením do oboru funkce. Pokud je volání funkce další příkaz. |
| f | Dokončit: spustí zbývající část rozsahu aktuální funkce a vrátí řízení volajícímu, (stejně jako krok out). |
| c, pokračování | pokračovat: spustí program až k další zarážce. |
| Q | Ukončí: ukončení relace ladění. |
| kde | Zobrazit zásobník: zobrazí zásobník volání v interaktivním okně. |
| Nápověda | Zobrazit nápovědu pro: Zobrazí dostupné příkazy v interaktivním okně. |
| &lt;výraz&gt; | vyhodnocení výrazu v *expr*. |

![Prohlížeče prostředí v interaktivním okně](media/debugger-environment-browser.png)
