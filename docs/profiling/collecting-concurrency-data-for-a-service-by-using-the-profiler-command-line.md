---
title: Shromažďování dat souběžnosti pro službu pomocí příkazového řádku profileru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4fe0d30077ede45910b0e62760c52e239beb213b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Shromažďování dat souběžnosti pro službu pomocí příkazového řádku profileru
Metoda souběžného zpracování z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci umožňuje shromažďování dat kolizí prostředku a data aktivity přístup z více vláken, která obsahuje využití je využití procesoru, kolizí přístup z více vláken, migrace přístup z více vláken, synchronizace zpoždění, oblasti překryté vstupně-výstupní operace, a jiných systémové události.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení ke službě spuštěné rozhraní .NET**|-   [Postupy: připojení profileru ke službě .NET ke shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Přidání dat interakce vrstvy**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Připojení ke službě spuštěné C/C++**|-   [Postupy: připojení profileru k nativní službě ke shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-windows-services"></a>Profilace služeb systému Windows  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilu pomocí metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Profilu pomocí metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Profile.NET kolekce přidělení a uvolnění paměti**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-concurrency-data"></a>Data profilování souběžného zpracování  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil samostatných aplikací**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profil webových aplikací ASP.NET**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-concurrency-data-views-and-reports"></a>Analýza dat souběžnosti zobrazeních a sestavách  
 [Zobrazení dat kolizí prostředku](../profiling/resource-contention-data-views.md)  
  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Odkaz  
 [Profilování nástroje pro příkazový řádek](../profiling/command-line-profiling-tools-reference.md)