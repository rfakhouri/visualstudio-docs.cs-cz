---
title: Shromažďování statistik aplikace pro službu pomocí metody vzorkování profileru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 07840ab2-3a92-4744-ac87-48b19e0ceecd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fc23456b6c27c27baf1134427ac449b8eb4090b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="collecting-application-statistics-for-services-by-using-the-profiler-sampling-method"></a>Shromažďování statistik aplikace pro službu pomocí metody vzorkování profileru
Tato část popisuje postupy a možnosti pro shromažďování statistik výkonu pro služby systému Windows pomocí metody vzorkování z příkazového řádku.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru ke službě .NET**|-   [Postupy: připojení profileru ke službě .NET ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)|  
|**Přidání dat interakce vrstvy**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Připojení profileru ke službě C/C++**|-   [Postupy: připojení profileru k nativní službě ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-windows-services"></a>Profilace služeb systému Windows  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilu pomocí metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**Profil .NET collection přidělení a uvolnění paměti**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Profil aktivita prostředku kolizí a přístup z více vláken**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  
### <a name="profiling-by-using-the-sampling-method"></a>Profilace pomocí metody vzorkování  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace samostatné (klient)**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profil webových aplikací ASP.NET**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Analýza dat vzorkování zobrazeních a sestavách  
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)