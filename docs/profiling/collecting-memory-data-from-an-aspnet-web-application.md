---
title: Shromažďování dat paměti pomocí příkazového řádku Profiler z webové aplikace ASP.NET | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 9772961d8ebd7b91b75886d7c5fa9cafbf76cfae
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53902864"
---
# <a name="collect-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Shromažďování dat paměti z webové aplikace ASP.NET pomocí příkazového řádku profileru
Tato část popisuje postupy a možnosti pro shromažďování paměť přidělení a objekt data o životním cyklu pro webovou aplikaci ASP.NET pomocí **VSPerfCmd** nástroj příkazového řádku.  
  
> [!NOTE]
>  **VSPerfCmd** nástroj vám poskytne úplný přístup k funkcím nástroje pro profilaci, včetně pozastavování a obnovování, profilování a shromažďovat další data z procesoru a čítače výkonu Windows. Můžete také použít **VSPerfASPNETCmd** nástroj příkazového řádku, pokud není nutné tuto funkci. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) nástroj příkazového řádku, žádné proměnné prostředí nutné nastavit a restartování počítače se nevyžaduje. Další informace najdete v tématu [profilace pohotová webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Běžné úkoly
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru k běžící aplikaci ASP.NET**|-   [Jak: Připojení profileru k webové aplikaci ASP.NET ke shromažďování dat paměti](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Instrumentace staticky kompilaci binárních souborů**|-   [Jak: Instrumentace staticky kompilované aplikace ASP.NET a shromažďování dat paměti](../profiling/how-to-instrument-a-statically-compiled-aspnet-app-and-collect-memory-data.md)|  
|**Dynamicky kompilovaných instrumentace binárních souborů**|-   [Jak: Instrumentace dynamicky kompilované aplikace ASP.NET a shromažďování dat paměti](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)|  
  
## <a name="related-tasks"></a>Související úlohy
  
### <a name="profile-aspnet-web-applications"></a>Webové aplikace ASP.NET profilu  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Profil s použitím metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Profil aktivita prostředku kolize a vlákna**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profile-net-framework-memory-data"></a>Profil dat o paměti rozhraní .NET Framework  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Profil služby**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyze-net-memory-data-views-and-reports"></a>Analýza zobrazení dat paměti .NET a sestavy  
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Odkaz  
 [Referenční dokumentace nástrojů příkazového řádku pro profilaci](../profiling/command-line-profiling-tools-reference.md)