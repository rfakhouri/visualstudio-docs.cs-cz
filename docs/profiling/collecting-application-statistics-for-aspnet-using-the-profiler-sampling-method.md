---
title: Shromažďovat statistiky pro technologii ASP.NET, webových aplikací | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 95991806f10a6b4821c232afcf09c83493fabe60
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930671"
---
# <a name="collect-statistics-for-aspnet-web-apps"></a>Shromáždit statistiku pro webové aplikace ASP.NET

Tato část popisuje postupy a možnosti pro shromažďování statistik výkonu pro webovou aplikaci ASP.NET pomocí **VSPerfASPNETCmd** a **VSPerfCmd** nástroj příkazového řádku a Metoda profilování vzorkování.  
  
> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  I když **VSPerfCmd** nástroj umožňuje úplný přístup k nástrojů pro profilaci sady funkcí, včetně pozastavování a obnovování profilace, a shromažďují další data z procesoru a čítače výkonu Windows, měli byste použít **VSPerfASPNETCmd** nástroje příkazového řádku, pokud není nutné tuto funkci. **VSPerfASPNETCmd** preferovanou metodu je nástroj příkazového řádku při se profilace webových stránek ASP.NET pomocí samostatného profileru. Ve srovnání s [VSPerfCmd](../profiling/vsperfcmd.md) nástroj příkazového řádku, žádné proměnné prostředí nutné nastavit a restartování počítače se nevyžaduje. Další informace najdete v tématu [profilace pohotová webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Běžné úkoly  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Připojení profileru k aplikaci ASP.NET**|-   [Jak: Připojení profileru k webové aplikaci ASP.NET ke shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profile-aspnet-web-applications"></a>Webové aplikace ASP.NET profilu  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil s použitím metody instrumentace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Profil přidělování a uvolňování paměti kolekce paměti**|-   [Shromažďování dat paměti](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|  
|**Profil aktivita prostředku kolize a vlákna**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="sample-method"></a>Ukázka metody  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profilovat samostatné (klientské) aplikace**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-stand-alone-applications.md)|  
|-   **Profil služby**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
  
### <a name="analyze-sampling-data-views-and-reports"></a>Analýza zobrazení dat vzorkování a sestavy  
 [Zobrazení dat metod vzorkování](../profiling/profiler-sampling-method-data-views.md)