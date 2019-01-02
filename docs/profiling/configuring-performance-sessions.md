---
title: Konfigurace výkonnostních relací | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- common tasks, performance
- common tasks, profiling tools
- profiling tools, common tasks
- performance, gathering data
ms.assetid: e1c3ba41-ffca-4edf-9a7f-8a5a9244ef9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7dd85cc1a4fb00acfc6d6f7afde05917552f6c2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53854331"
---
# <a name="configure-performance-sessions"></a>Konfigurace výkonnostních relací
S použitím [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci, můžete shromažďovat celou řadu údaje o výkonu pro mnoho typů aplikací. Tato část ukazuje, jak používat výkonu Wizardand vlastnosti relace výkonu a cílový binární soubor ke konfiguraci nástroje pro profilaci sady ke shromažďování dat, která vás zajímá. Vlastnosti konfigurace nástroje pro profilaci můžete použít také k řízení množství dat shromažďovaných během spuštění profilování. Další informace najdete v tématu [sběr dat řídit](../profiling/controlling-data-collection.md).  
  
> [!NOTE]
>  V mnoha případech použití výchozí vlastnosti Průvodce výkonu je efektivní způsob shromažďování dat profilování. Další informace najdete v tématu [začátečníky Průvodce profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md) a [Začínáme](../profiling/getting-started-with-performance-tools.md).  
  
## <a name="common-tasks"></a>Běžné úkoly
  
| Úloha | Související obsah |
| - | - |
| **Nastavení základní profilování možností:** Měli byste nakonfigurovat [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] používat Microsoft symbol server. Tím zajistíte, že máte přístup k symbolům, jako je například funkce a parametr názvy pro aktuální verzi Windows a jiné aplikace od Microsoftu. Další obecné možnosti můžete také určit před spuštěním relace profilování, jako jsou oprávnění systému a nástrojů pro profilaci a názvy souborů dat profilování. | -   [Jak: Referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)<br />-   [Jak: Serializace informací o symbolu](../profiling/how-to-serialize-symbol-information.md)<br />-   [Jak: Nastavení aktuální relace](../profiling/how-to-set-the-current-session.md)<br />-   [Jak: Nastavení oprávnění](../profiling/how-to-set-permissions.md)<br />-   [Jak: Nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md) |
| **Zadejte data, která chcete shromažďovat:** Postupy, které můžete použít ke konfiguraci relace profilování závisí na typu cílovou aplikaci, kterou chcete do profilu a zadejte údaje o výkonu, které chcete shromažďovat. | -   [Jak: Výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)<br />-   [Shromažďování statistik výkonu pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)<br />-   [Shromažďování dat o přidělování a životnosti paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)<br />-   [Jak: Profilování kódu JavaScript ve webových stránkách](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Shromažďování dat o souběžnosti vláken a procesů](../profiling/collecting-thread-and-process-concurrency-data.md)<br />-   [Shromažďování dalších dat o výkonu](../profiling/collecting-additional-performance-data.md) |
| **Nastavit možnosti pokročilé konfigurace:** Při profilování aplikace rozhraní .NET Framework, které načítají více verzí common language runtime (CLR), můžete určit, kterou verzi profilu. Pokud máte víc souborů .exe v relaci výkonu, můžete nastavit pořadí spouštění binárních souborů. | -   [Jak: Určení modulu runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)<br />-   [Jak: Určení binárního souboru ke spuštění](../profiling/how-to-specify-the-binary-to-start.md) |
  
## <a name="related-sections"></a>Související oddíly  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)  
  
## <a name="see-also"></a>Viz také:  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)