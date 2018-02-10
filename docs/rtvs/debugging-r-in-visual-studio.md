---
title: "Ladění pomocí nástroje R pro sadu Visual Studio | Microsoft Docs"
description: "Visual Studio poskytuje úplné ladění prostředí pro R včetně zarážky, připojení, volejte zásobníku a zkontrolujete proměnné."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 185896840be089c8a74e018e3fd66fa2816c5d76
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="debugging-r-in-visual-studio"></a>Ladění R v sadě Visual Studio

R nástrojů pro Visual Studio (RTVS) se integruje s úplné ladění prostředí sady Visual Studio (viz [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md). Tato podpora zahrnuje zarážky, připojení ke spuštěným procesům, proměnné provádějící kontrolu a sledováním a zkontrolujete zásobníku volání. V tomto článku, pak jsou zde popsány aspekty o ladění, které jsou jedinečné pro R a RTVS.

Spuštění ladicího programu pro spuštění R soubor v projektu R je stejné jako u jiných typů projektů: použijte **ladění > Spustit ladění**, klávesy F5 nebo **zdrojový soubor spouštěcí** na panelu nástrojů ladění: 

![Ladicí program tlačítko start pro R](media/debugger-start-button.png)

Chcete-li změnit po spuštění souboru, soubor v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **nastavit jako spouštěcí R skript**.

Ve všech případech spuštění ladicího programu "zdroje" soubor v okně interaktivní, což znamená jeho načítání a se tam spuštěná jako zobrazené ve výstupu interaktivních okna:

```output
> rtvs::debug_source("c:/proj/rproject1/rproject1/script.R")
Sourcing: c:\proj\rproject1\rproject1\script.R
Sourcing: c:\proj\rproject1\rproject1\Settings.R
```

Všimněte si, že `rtvs::debug_source` funkce slouží k zdroje skriptu. Tato funkce není nutná, protože RTVS je potřeba upravit kód v rámci přípravy pro ladění. Při připojení pomocí žádné zdrojové příkaz RTVS a ladicí program Visual Studio automaticky použije `rtvs::debug_source`.

Můžete také ručně připojit ladicí program z okna interaktivní přímo pomocí **R nástroje > relace > připojit ladicí program** příkazu, **ladění > připojit k R interaktivní** příkaz nebo  **Připojit ladicí program** příkazu na panelu nástrojů interaktivních okna. Po dokončení tak je vaší povinností zdrojové soubory, které chcete ladit. Pokud chcete ručně zdrojové soubory, ujistěte se, že používáte `rtvs::debug_source` a ne regulární `source` příkazu v jazyce R.

Toto připojení mezi ladicího programu a interaktivních okna usnadňuje provádět akce, jako je volání (a ladění) funkce s jiným parametrem hodnotami. Předpokládejme například, že máte následující funkci v souboru z domácích zdrojů (tj., který je načten do relace):

```R
add <- function(x, y) {
    return(x + y)
}
```

Pak můžete nastavit zarážky `return` příkaz. Nyní, v okně interaktivní zadávání `add(4,5)` zastaví ladicí program na vaší zarážce.

## <a name="environment-browser-in-the-interactive-window"></a>Prostředí prohlížeče v okně interaktivní

Po zastavení v ladicím programu je také zastavit v řádku prostředí prohlížeče ve [interaktivních okna](interactive-repl-for-r-in-visual-studio.md). Výzva se zobrazí jako `Browse[n]>` kde n je číslo.

Prohlížeč prostředí podporuje řadu příkazů, speciální:

| Příkaz | Popis |
| --- | --- |
| n | Další: spustí další příkaz v kódu souboru (stejné jako krok přes). |
| s | Krokování s vnořením: spustí další příkaz do souboru kódu zanoříte se do oboru funkce, pokud další je volání funkce. |
| f | Dokončit: spustí zbytek aktuální obor funkce a vrátí volajícímu (stejný jako krok out). |
| c, potřeba | pokračovat: program spustí další zarážku. |
| Q | Ukončí: končí relaci ladění. |
| kde | Zobrazit zásobník: zobrazí v okně interaktivní zásobníku volání. |
| Nápověda | Zobrazit nápovědu: zobrazí v okně interaktivní dostupné příkazy. |
| &lt;expr&gt; | vyhodnocení výrazu v *expr*. |

![Prostředí prohlížeče v okně interaktivní](media/debugger-environment-browser.png)
