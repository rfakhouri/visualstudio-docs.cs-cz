---
title: "Shromažďování dat souběžnosti pro samostatné aplikace pomocí příkazového řádku profileru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- concurrency profiling method
- profiling tools,concurrency method
ms.assetid: 0a2c6d8a-50b3-48aa-b617-9137b049d21e
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91e079fa996c30160454dcd7f8cc3d3bade27b2d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line"></a>Shromažďování dat souběžnosti pro samostatné aplikace pomocí příkazového řádku profileru
Metoda souběžného zpracování z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci umožňuje shromažďování dat kolizí prostředku a data aktivity přístup z více vláken, která obsahuje využití je využití procesoru, kolizí přístup z více vláken, migrace přístup z více vláken, synchronizace zpoždění, oblasti překryté vstupně-výstupní operace, a jiných systémové události.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spuštění rozhraní .NET Framework aplikace a profil dat souběžnosti**|-   [Postupy: spuštění aplikace rozhraní .NET Framework ke shromažďování dat souběžnosti](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Spustit dat souběžnosti aplikaci a profilu C/C++**|-   [Postupy: spuštění nativní aplikace za účelem shromáždění dat souběžnosti](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Připojení profileru k spuštěné aplikace rozhraní .NET Framework**|-   [Postupy: připojení profileru k aplikaci .NET Framework ke shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Připojení profileru k spuštěné aplikace C/C++**|-   [Postupy: připojení profileru k nativní aplikaci a shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-stand-alone-applications"></a>Profilace samostatných aplikací  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilu pomocí metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profilu pomocí metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Profil .NET collection přidělení a uvolnění paměti**|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Přidání dat interakce vrstvy**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
### <a name="profiling-concurrency-issues"></a>Profilace potíže se souběžností  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace ASP.NET**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
|**Profil služby**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>Analýza dat souběžnosti zobrazeních a sestavách  
 [Zobrazení dat kolizí prostředku](../profiling/resource-contention-data-views.md)  
  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Odkaz  
 [Profilování nástroje pro příkazový řádek](../profiling/command-line-profiling-tools-reference.md)