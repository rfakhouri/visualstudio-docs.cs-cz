---
title: Shromažďování statistik aplikace pro službu pomocí metody vzorkování Profiler | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 07840ab2-3a92-4744-ac87-48b19e0ceecd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1de40418af63c3d5a963bd83a59c916c87251b5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961582"
---
# <a name="collect-application-statistics-for-services-by-using-the-profiler-sampling-method"></a>Shromažďování statistik aplikace pro službu pomocí metody vzorkování profileru
Tato část popisuje postupy a možnosti pro shromažďování statistik výkonu pomocí metody vzorkování z příkazového řádku služeb Windows.  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Běžné úkoly  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru ke službě .NET**|-   [Jak: Připojení profileru ke službě .NET ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)|  
|**Přidání dat interakce vrstev**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Připojení profileru ke službě jazyka C/C++**|-   [Jak: Připojení profileru k nativní službě ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profile-windows-services"></a>Profil služby Windows  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
|**Profilování paměti .NET přidělování a uvolňování paměti kolekce**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Profil aktivita prostředku kolize a vlákna**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
  

### <a name="profile-by-using-the-sampling-method"></a>Profil s použitím metody vzorkování  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications.md)|  
|**Profilovat webové aplikace ASP.NET**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
  
### <a name="analyze-sampling-data-views-and-reports"></a>Analýza zobrazení dat vzorkování a sestavy  
 [Zobrazení dat metod vzorkování](../profiling/profiler-sampling-method-data-views.md)
