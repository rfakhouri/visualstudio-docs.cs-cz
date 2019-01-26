---
title: Shromažďování podrobných dat časování pro webovou aplikaci ASP.NET pomocí metody instrumentace Profiler z příkazového řádku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,instrumentation method
- instrumentation profiling method
ms.assetid: 29f2fc55-aaf7-4e18-a672-8815455fba73
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 1b8632a469a04a24c53ddb80d3b0fba720690d52
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952909"
---
# <a name="collect-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line"></a>Shromažďování podrobných dat časování pro webovou aplikaci ASP.NET pomocí metody instrumentace profileru z příkazového řádku
Tato část popisuje postupy a možnosti pro shromažďování podrobných výkonu dat pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci s použitím **VSPerfCmd** nástroj příkazového řádku a metody instrumentace.  
  
> [!NOTE]
>  **VSPerfCmd** nástroj vám poskytne úplný přístup k funkcím nástroje pro profilaci, včetně pozastavování a obnovování, profilování a shromažďovat další data z procesoru a čítače výkonu Windows. Můžete také použít **VSPerfASPNETCmd** nástroj příkazového řádku, pokud není nutné tuto funkci. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) nástroj příkazového řádku, musí být nastaveny žádné proměnné prostředí a restartování počítače se nevyžaduje. Další informace najdete v tématu [profilace pohotová webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  

## <a name="common-tasks"></a>Běžné úkoly  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil staticky kompilované binární soubory**|-   [Jak: Instrumentace staticky kompilované aplikace ASP.NET a shromažďování podrobných dat časování](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)|  
|**Profilování dynamicky kompilovaných binárních souborů**|-   [Jak: Instrumentace dynamicky kompilované aplikace ASP.NET a shromažďování podrobných dat časování](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)|  
  

## <a name="related-tasks"></a>Související úlohy

  
### <a name="profile-aspnet-web-applications"></a>Webové aplikace ASP.NET profilu  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody vzorkování**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Profil přidělování a uvolňování paměti kolekce paměti**|-   [Shromažďování dat paměti](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|  
|**Profil aktivita prostředku kolize a vlákna**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profile-by-using-the-instrumentation-method"></a>Profil s použitím metody instrumentace  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|  
|**Profil služby**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|  
  
### <a name="analyze-instrumentation-data-views-and-reports"></a>Analýza zobrazení dat instrumentace a sestavy  
 [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)