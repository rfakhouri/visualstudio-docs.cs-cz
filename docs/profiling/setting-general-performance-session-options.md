---
title: Možnosti nastavení obecných výkonnostní relace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.general
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5268e6821714dc6850541c319dba450bcc04490b
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="set-general-performance-session-options"></a>Nastavení možností relace obecný výkon

Můžete nastavit metodu kolekce a profilování data zásady vytváření názvů pro výkonnostní relace profilace nástroje sady Visual Studio na **Obecné** stránky dialogové okno Vlastnosti výkonnostní relace. Chcete-li otevřít dialogové okno z **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

## <a name="choosing-data-collection-methods"></a>Výběr metody shromažďování dat

Nastavte jako metodu základní kolekce tak, že vyberete jednu z možností v části **profilace kolekce**. Tyto možnosti jsou popsány v následující tabulce je následující:

|||
|-|-|
|**Vzorkování**. Metoda vzorkování shromažďuje profilování informace v pravidelných intervalech. Tato metoda je užitečná pro hledání problémy s využitím procesoru a je navržené způsob spuštění většina vyšetřování výkonu.|- [Shromažďování statistik výkonu pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)|
|**Instrumentace**. Metoda instrumentace vloží do kopie modul profilace kód, který zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilace spustit. Tato metoda je užitečná pro shromažďování časování podrobné informace o části kódu a porozumění vlivu vstupních a výstupních operací na výkon aplikace.|- [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|
|**Concurrency**. Metoda souběžného zpracování shromažďuje data pro všechny události, že bloky provádění kódu, například když vlákno čeká uzamčena přístup k prostředku aplikace na uvolnění. Tato metoda je užitečná pro analýzu vícevláknové aplikace.|- [Shromažďování dat souběžnosti proces a přístup z více vláken](../profiling/collecting-thread-and-process-concurrency-data.md)|

 Pomocí metody vzorkování nebo instrumentace můžete shromažďování dat paměti .NET. Vyberte typ dat v rámci **profilace paměti .NET**.

|||
|-|-|
|**Shromažďování informací o přidělení objektu .NET**. Ve výchozím nastavení data zahrnují počet a velikost přidělené objektů. Vyberte nebo zrušte zaškrtnutí tohoto políčka k povolení nebo zakázání shromažďování dat paměti .NET. |- [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|
|**Taky shromažďovat informace o doba života objektu .NET**. Výběrem tohoto zaškrtávacího políčka zahrnovat údaje o kolekci generace uvolňování paměti, které jste použili k uvolnění paměti objekty.|- [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)  |

 Stránka relace profilování se zobrazí, jakmile začnete profilovat aplikaci. Na této stránce můžete profilování pozastavit, obnovit a zastavit.

 ![Profilování relace stránky](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")

## <a name="set-profiling-data-file-options"></a>Nastavení možností datového souboru profilace

|||
|-|-|
|**Sestava**. Ve výchozím nastavení profilaci soubor dat (.vsp) je uveden název PROFILOVANÉHO aplikace a je umístěn ve složce řešení nebo produktu project. Řetězec datum je také připojeným k názvu a zvýšena číslo se přidá do datové soubory, které by jinak mají duplicitní názvy. Tato nastavení můžete změnit.|- [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|