---
title: Shromažďování dat souběžnosti pro službu pomocí příkazového řádku Profiler | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 275aacba-b2af-4d34-8931-ee30d777a256
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a782c57fcbadc40839c652b5fbd89ca3ba47179
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949534"
---
# <a name="collect-concurrency-data-for-a-service-by-using-the-profiler-command-line"></a>Shromažďování dat souběžnosti pro službu pomocí příkazového řádku profileru
Za použití metody souběžnosti z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady umožňuje shromažďovat data kolize prostředků a data o činnosti vlákna, která ukazuje využití procesor, kolize vlákna, migrace vlákna, zpoždění synchronizace, oblasti překryté vstupně-výstupní operace a další systémové události.  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Běžné úkoly  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojit ke spuštěné službě rozhraní .NET**|-   [Jak: Připojení profileru ke službě .NET ke shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Přidání dat interakce vrstev**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Připojit ke spuštěné službě jazyka C/C++**|-   [Jak: Připojení profileru k nativní službě ke shromažďování dat souběžnosti](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profile-windows-services"></a>Profil služby Windows  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Profil s použitím metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
|**Přidělování a uvolňování paměti kolekce Profile.NET**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="profile-concurrency-data"></a>Profil dat souběžnosti  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Samostatné aplikace profilu**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|  
|**Profilovat webové aplikace ASP.NET**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="analyze-concurrency-data-views-and-reports"></a>Analýza souběžnosti zobrazení dat a sestav  
 [Zobrazení dat kolizí prostředku](../profiling/resource-contention-data-views.md)  
  
 [Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)  
  
## <a name="reference"></a>Odkaz  
 [Referenční dokumentace nástrojů příkazového řádku pro profilaci](../profiling/command-line-profiling-tools-reference.md)