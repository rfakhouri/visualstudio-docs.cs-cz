---
title: "Možnosti nastavení obecných výkonnostní relace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.general
ms.assetid: 6b60bd1b-2198-4261-b84e-9b2d8494a992
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8ca1f5d0c310fa4f9d75f27c6baf73f7a230e87e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="setting-general-performance-session-options"></a>Nastavení obecných možností výkonnostní relace
Můžete nastavit metodu kolekce a profilace data konvence pojmenování [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci výkonnostní relace na **Obecné** stránky dialogové okno Vlastnosti výkonnostní relace. Chcete-li otevřít dialogové okno z **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## <a name="choosing-data-collection-methods"></a>Výběr metody shromažďování dat  
 Nastavte jako metodu základní kolekce tak, že vyberete jednu z možností v části **profilace kolekce**. Tyto možnosti jsou popsány v následující tabulce je následující:  
  
|||  
|-|-|  
|**Vzorkování**. Metoda vzorkování shromažďuje profilování informace v pravidelných intervalech. Tato metoda je užitečná pro hledání problémy s využitím procesoru a je navržené způsob spuštění většina vyšetřování výkonu.|-   [Shromažďování statistik výkonu pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)|  
|**Instrumentace**. Metoda instrumentace vloží do kopie modul profilace kód, který zaznamenává každou položku, ukončení a volání funkce funkce v modulu během profilace spustit. Tato metoda je užitečná pro shromažďování časování podrobné informace o části kódu a porozumění vlivu vstupních a výstupních operací na výkon aplikace.|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|  
|**Concurrency**. Metoda souběžného zpracování shromažďuje data pro všechny události, že bloky provádění kódu, například když vlákno čeká uzamčena přístup k prostředku aplikace na uvolnění. Tato metoda je užitečná pro analýzu vícevláknové aplikace.|-   [Shromažďování dat souběžnosti proces a přístup z více vláken](../profiling/collecting-thread-and-process-concurrency-data.md)|  
  
 Pomocí metody vzorkování nebo instrumentace můžete shromažďování dat paměti .NET. Vyberte typ dat v rámci **profilace paměti .NET**.  
  
|||  
|-|-|  
|**Shromažďování informací o přidělení objektu .NET**. Ve výchozím nastavení data zahrnují počet a velikost přidělené objektů. Vyberte nebo zrušte zaškrtnutí tohoto políčka k povolení nebo zakázání shromažďování dat paměti .NET.<br /><br /> **Taky shromažďovat informace o doba života objektu .NET**. Výběrem tohoto zaškrtávacího políčka zahrnovat údaje o kolekci generace uvolňování paměti, které jste použili k uvolnění paměti objekty.|-   [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|  
  
 Stránka relace profilování se zobrazí, jakmile začnete profilovat aplikaci. Na této stránce můžete profilování pozastavit, obnovit a zastavit.  
  
 ![Profilování relace stránky](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")  
  
## <a name="setting-profiling-datra-file-options"></a>Nastavení možností datového souboru profilování  
  
|||  
|-|-|  
|**Sestava**. Ve výchozím nastavení profilaci soubor dat (.vsp) je uveden název PROFILOVANÉHO aplikace a je umístěn ve složce řešení nebo produktu project. Řetězec datum je také připojeným k názvu a zvýšena číslo se přidá do datové soubory, které by jinak mají duplicitní názvy. Tato nastavení můžete změnit.|-   [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|