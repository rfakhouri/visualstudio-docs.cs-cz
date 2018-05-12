---
title: Shromáždit statistiku pro technologii ASP.NET webové aplikace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, sampling method
- sampling profling method
ms.assetid: f8383ab1-eb49-4d3f-8608-d8b4d51a81be
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 9be304398fcefaf6a38ca7e1d557f2c9146b4872
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="collect-statistics-for-aspnet-web-apps"></a>Shromažďování statistik pro webové aplikace ASP.NET

Tato část popisuje postupy a možnosti pro shromažďování statistik výkonu pro webovou aplikaci ASP.NET pomocí **VSPerfASPNETCmd** a **VSPerfCmd** nástroj příkazového řádku a Metoda profilace se vzorkováním.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  I když **VSPerfCmd** nástroj umožňuje úplný přístup k nástrojích pro profilaci funkcí, včetně pozastavení a obnovení profilování, a získání dalších dat z procesoru a čítačů výkonu systému Windows, měli byste použít **VSPerfASPNETCmd** nástroje příkazového řádku, pokud není nutné tuto funkci. **VSPerfASPNETCmd** nástroj pro příkazový řádek je upřednostňovaná metoda při vaší jsou profilace ASP.NET – webové servery pomocí samostatného profileru. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) žádné proměnné prostředí je nutné nastavit nástroj pro příkazový řádek, a není vyžadováno restartování počítače. Další informace najdete v tématu [rychlé profilace webu pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru k aplikaci ASP.NET**|-   [Postupy: připojení profileru k webové aplikaci ASP.NET ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-aspnet-web-applications"></a>Profilace webových aplikací ASP.NET  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilu pomocí metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Profil kolekce přidělení a uvolnění paměti**|-   [Shromažďování dat paměti](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|  
|**Profil aktivita prostředku kolizí a přístup z více vláken**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="sampling-method"></a>Metoda vzorkování  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil aplikace samostatné (klient)**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications.md)|  
|-   **Profil služby**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Analýza dat vzorkování zobrazeních a sestavách  
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)