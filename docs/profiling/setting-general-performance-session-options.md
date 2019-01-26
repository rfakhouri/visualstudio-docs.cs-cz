---
title: Relace výkonu nastavení obecných možností | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.general
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4cc99869276588da43a897e7b087f6e1251651b7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026772"
---
# <a name="set-general-performance-session-options"></a>Nastavení obecných možností výkonnostní relace

Metoda kolekce a profilování dat zásady vytváření názvů pro relace výkonu profilace nástroje sady Visual Studio můžete nastavit **Obecné** stránky dialogové okno Vlastnosti relace výkonu. Chcete-li otevřít toto dialogové okno z **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu a pak klikněte na tlačítko **vlastnosti**.

## <a name="choosing-data-collection-methods"></a>Výběr metody kolekce dat

Nastavte jako metodu základní kolekce tak, že vyberete jednu z možností v části **sběr dat profilace**. Tyto možnosti jsou popsány v následující tabulce:

|||
|-|-|
|**Vzorkování**. Metoda vzorkování shromažďuje profilování informace v pravidelných intervalech. Tato metoda je užitečná pro vyhledání problémy s využitím procesoru a je navržený způsob spuštění většina vyšetřování výkonu.|- [Shromažďování statistik výkonu pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)|
|**Instrumentace**. Metoda instrumentace vkládá do kopie modulu profilace kód, který zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilování. Tato metoda je užitečná pro shromažďování podrobných informací o časování o části kódu a pochopení dopadu vstupních a výstupních operací na výkon aplikace.|- [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|
|**Souběžnost**. Za použití metody souběžnosti shromažďuje data pro každou událost, pozastaví spuštění kódu, například když vlákno čeká uzamčen přístup k prostředku aplikace k uvolnění. Tato metoda je užitečná pro analýzu vícevláknových aplikacích.|- [Shromažďování dat souběžnosti proces a vlákna](../profiling/collecting-thread-and-process-concurrency-data.md)|

 Můžete shromažďování dat paměti .NET pomocí metody vzorkování nebo instrumentace. Vyberte typ dat v rámci **profilování paměti .NET**.

|||
|-|-|
|**Shromáždit informace o přidělování objektů .NET**. Ve výchozím nastavení data zahrnují počet a velikost přidělené objekty. Zaškrtněte nebo zrušte zaškrtnutí políčka Povolit nebo zakázat shromažďování dat paměti .NET. |- [Shromažďuje alokaci paměti .NET a Data o životním cyklu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|
|**Také shromažďovat informace o životnosti objektů .NET**. Zaškrtněte toto políčko obsahují data o generací kolekce uvolňování paměti, které byly použity pro uvolnění paměti objektů.|- [Shromažďuje alokaci paměti .NET a Data o životním cyklu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md) |

 Stránka relace profilování se zobrazí, jakmile začnete profilovat aplikaci. Na této stránce můžete profilování pozastavit, obnovit a zastavit.

 ![Stránce relace profilování](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")

## <a name="set-profiling-data-file-options"></a>Nastavení možností datového souboru profilace

|||
|-|-|
|**Sestava**. Ve výchozím nastavení souboru dat profilování (.vsp) je přiřazen název profilované aplikace a je umístěn ve složce řešení nebo projektu. Řetězec datum je také připojeným k názvu a zvyšující číslo je přidán do datových souborů, které by jinak mít duplicitní názvy. Tato nastavení můžete změnit.|- [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|