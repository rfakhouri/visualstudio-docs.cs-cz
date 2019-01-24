---
title: Shromažďování dat paměti pomocí příkazového řádku Profiler z webové aplikace ASP.NET | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 373e20ba3130cc5b5c633ef58f104d8cb8112ae3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758528"
---
# <a name="collecting-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Shromažďování dat paměti z webové aplikace ASP.NET pomocí příkazového řádku profileru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato část popisuje postupy a možnosti pro shromažďování paměť přidělení a objekt data o životním cyklu pro webovou aplikaci ASP.NET pomocí **VSPerfCmd** nástroj příkazového řádku.  
  
> [!NOTE]
>  **VSPerfCmd** nástroj vám poskytne úplný přístup k funkcím nástroje pro profilaci, včetně pozastavování a obnovování, profilování a shromažďovat další data z procesoru a čítače výkonu Windows. Můžete také použít **VSPerfASPNETCmd** nástroj příkazového řádku, pokud není nutné tuto funkci. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) nástroj příkazového řádku, žádné proměnné prostředí nutné nastavit a restartování počítače se nevyžaduje. Další informace najdete v tématu [rychlé webových profilů stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru k běžící aplikaci ASP.NET**|-   [Jak: Připojení profileru k webové aplikaci ASP.NET kvůli shromáždění dat o paměti](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Instrumentace staticky kompilaci binárních souborů**|-   [Jak: Instrumentace staticky kompilované aplikace ASP.NET a shromáždění dat o paměti](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
|**Dynamicky kompilovaných instrumentace binárních souborů**|-   [Jak: Instrumentace dynamicky kompilované aplikace ASP.NET a shromáždění dat o paměti](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-aspnet-web-applications"></a>Profilace webových aplikací ASP.NET  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-web-applications-using-the-profiler-sampling-method-from-the-command-line.md)|  
|**Profil s použitím metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](/visualstudio/profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method?view=vs-2015)|  
|**Profil aktivita prostředku kolize a vlákna**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application-using-the-profiler-command-line.md)|  
  
### <a name="profiling-net-framework-memory-data"></a>Profilování dat paměti .NET Framework  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Profil služby**|-   [Shromažďování dat paměti .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyzing-net-memory-data-views-and-reports"></a>Analýza dat o paměti .NET zobrazeních a sestavách  
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Odkaz  
 [Referenční dokumentace nástrojů příkazového řádku pro profilaci](../profiling/command-line-profiling-tools-reference.md)
