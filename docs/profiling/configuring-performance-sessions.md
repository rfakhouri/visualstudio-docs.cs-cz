---
title: "Konfigurace výkonnostních relací | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- common tasks, performance
- common tasks, profiling tools
- profiling tools, common tasks
- performance, gathering data
ms.assetid: e1c3ba41-ffca-4edf-9a7f-8a5a9244ef9b
caps.latest.revision: "36"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bc896429c3d9e9307fd17a7727228770735af64
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="configuring-performance-sessions"></a>Konfigurace výkonnostních relací
Pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci, můžete shromáždit celou řadu údaje o výkonu pro velký počet typů aplikací. V této části se dozvíte, jak pomocí výkonu Wizardand vlastnosti výkonnostní relace a cílový binární soubor konfigurace nástrojů profilace ke shromažďování dat, které vás zajímají. Vlastnosti konfigurace nástroje pro profilaci můžete použít také k řízení množství dat, které se shromažďují v profilaci spustit. Další informace najdete v tématu [řízení shromažďování dat](../profiling/controlling-data-collection.md).  
  
> [!NOTE]
>  V řadě případů použití výchozí vlastnosti Průvodce výkonu je efektivní způsob shromažďování dat o profilování. Další informace najdete v tématu [Průvodce začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md) a [Začínáme](../profiling/getting-started-with-performance-tools.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Nastavení možností základní profilování:** byste měli nakonfigurovat [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] použití serveru Microsoft symbol. Tím se přesvědčíte, že máte přístup k symboly, například názvy funkce a parametrů pro aktuální verze systému Windows a jiných aplikací společnosti Microsoft. Můžete také určit další obecné možnosti před zahájením relace profilování, jako jsou oprávnění systému a nástrojů pro profilaci a názvy datových souborů profilace.|-   [Postupy: referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)<br />-   [Postupy: serializace informací o symbolu](../profiling/how-to-serialize-symbol-information.md)<br />-   [Postupy: nastavení aktuální relace](../profiling/how-to-set-the-current-session.md)<br />-   [Postupy: nastavení oprávnění](../profiling/how-to-set-permissions.md)<br />-   [Postupy: nastavení možností názvu datového souboru výkonu](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**Určete data, která chcete shromažďovat:** postupy, které můžete použít ke konfiguraci relace profilování závisí na typ cílové aplikace, které chcete profil a typu dat výkonu, který chcete shromáždit.|-   [Postupy: výběr metod kolekcí](../profiling/how-to-choose-collection-methods.md)<br />-   [Shromažďování statistik výkonu pomocí vzorkování](../profiling/collecting-performance-statistics-by-using-sampling.md)<br />-   [Shromažďování dat životnost a přidělení paměti .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)<br />-   [Postupy: profilování kódu JavaScript ve webové stránky](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Shromažďování dat souběžnosti proces a přístup z více vláken](../profiling/collecting-thread-and-process-concurrency-data.md)<br />-   [Shromažďování další Data o výkonu](../profiling/collecting-additional-performance-data.md)|  
|**Nastavit Upřesnit možnosti konfigurace:** při profil aplikace rozhraní .NET Framework, které načítají více verzí běžné language runtime (CLR) můžete určit, která verze profilu. Pokud máte víc souborů .exe v relaci výkonu, můžete nastavit pořadí spuštění binárních souborů.|-   [Postupy: Zadejte modul Runtime rozhraní .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)<br />-   [Postupy: určení binárního souboru spuštění](../profiling/how-to-specify-the-binary-to-start.md)|  
  
## <a name="related-sections"></a>Související oddíly  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)