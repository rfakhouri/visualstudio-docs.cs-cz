---
title: Shromažďování statistik výkonu pomocí vzorkování | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,sampling
- sampling profiling method
ms.assetid: 8e36361b-bb3d-40c6-b286-0e68c0ecb915
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0b84674eafde85528e04157ab213913e57d27e60
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439028"
---
# <a name="collecting-performance-statistics-by-using-sampling"></a>Shromažďování statistik výkonu pomocí vzorkování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve výchozím nastavení [!INCLUDE[vsPreShort](../includes/vspreshort-md.md)] metody nástroje pro profilaci vzorkování shromažďuje informace o vytváření profilů každých 10 000 000 cyklů procesoru (přibližně každých-setiny sekundy v počítači se 1 GHz). Metody vzorkování je užitečné pro vyhledání problémy s využitím procesoru a je navržený způsob spuštění většina vyšetřování výkonu.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. Aplikace Windows Store také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Metoda vzorkování můžete zadat pomocí jedné z následujících postupů:  
  
- Klikněte na první stránce průvodce Profilováním, **vzorkování procesoru (doporučeno)**.  
  
- Na **prohlížeč výkonu** nástrojů v **metoda** klikněte na možnost **vzorkování**.  
  
- Na **Obecné** stránky dialogovém okně Vlastnosti relace výkonu můžete kliknout na tlačítko **vzorkování**.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete zadat další možnosti v _relace výkonu_**stránky vlastností** dialogovému oknu relace výkonu. Chcete-li otevřít toto dialogové okno:  
  
- V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na tlačítko **vlastnosti**.  
  
  Úkoly v následující tabulce popisují možnosti, které můžete určit _relace výkonu_**stránky vlastností** dialogové okno při profilování pomocí metody vzorkování.  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|Na **Obecné** stránce, přidejte alokaci paměti .NET a shromažďování dat životnost a pojmenování detailů generovaného souboru dat profilování (.vsp).|-   [Shromažďuje alokaci paměti .NET a Data o životním cyklu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Na **vzorkování** stránce, změna míry vzorkování, změní událost odběru vzorků z hodinových cyklů procesoru na jiný čítač výkonu procesoru nebo obě tyto hodnoty změnit...|-   [Jak: Výběr událostí vzorkování](../profiling/how-to-choose-sampling-events.md)|  
|Na **spuštění** stránky, zadejte aplikaci, aby začala a na začátek pořadí, pokud máte několik projektů .exe ve vašem kódu řešení.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **interakce vrstev** stránce, přidejte informace o volání ADO.NET na data shromažďovaná v theprofiling spustit.|-   [Shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md)|  
|Na **události Windows** stránky, zadejte jeden nebo více událostí trasování událostí pro Windows (ETW) pro shromažďování dat prostřednictvím data vzorkování.|-   [Jak: Shromažďování dat o trasování událostí pro Windows](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Na **čítače Windows** stránky, zadejte jeden nebo více čítačů výkonu operačního systému pro přidání do profilových dat. jako značky.|-   [Jak: Shromažďování dat z čítačů Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Na **Upřesnit** stránky, zadejte verzi modulu runtime rozhraní .NET Framework do profilu, pokud vaše aplikace moduly používat více verzí. Standardně je první verze načíst profilována.|-   [Jak: Určení modulu runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|
