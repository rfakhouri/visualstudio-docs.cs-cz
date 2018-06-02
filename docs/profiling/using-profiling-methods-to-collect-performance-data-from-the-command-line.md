---
title: Použití metod profilace ke shromažďování dat výkonu z příkazového řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 141341c09d9028e90900a29c702667304cfea7f7
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477703"
---
# <a name="use-profiling-methods-to-collect-performance-data-from-the-command-line"></a>Použití metod profilace ke shromažďování dat výkonu z příkazového řádku
Vaši volbu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje a možnosti závisí na faktorech, jako je například typ aplikace, můžete se profilování, profilování metody, která chcete použít, a jestli je cílová aplikace napsané v nativní nebo [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]kódu.  
  
 V tomto tématu slouží k uspořádání příkazového řádku procedurální témata profilování metodou, který zvolíte.  
  
## <a name="use-the-sampling-method-to-collect-performance-statistics"></a>Shromažďování statistik výkonu pomocí metody vzorkování  
 Metoda vzorkování nástrojích pro profilaci shromažďuje údaje o výkonu v určených intervalech v profilaci spustit. Vzorkování dat může poskytovat přehled problémy s výkonem vázané na procesor a může být dobrým způsobem, jak začít vyhledávat výkon aplikace.  
  
 Můžete začít s profilerem a aplikace ve stejnou dobu, nebo můžete připojení profileru k spuštěnou instanci aplikace.  
  
|Úloha|Typ cílové aplikace|  
|----------|-----------------------------|  
|**Spuštění aplikace**|-   [Samostatné aplikace](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Připojit k spuštěných procesů**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)<br />-   [Nativní samostatné aplikace](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)<br />-   [Webové aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Nativní služby](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|  
  
## <a name="use-the-instrumentation-method-to-collect-detailed-timing-data"></a>Shromažďování podrobných dat časování pomocí metody instrumentace  
 Metoda instrumentace nástrojích pro profilaci shromažďuje údaje o výkonu z kopie binární soubory aplikace, které obsahují software sondy na informace o záznamu výkonu. Instrumentace data jsou shromažďována na začátku a konci každé instrumentovaného funkce a v každé volání jiných funkcí z instrumentovaného funkce. Metoda instrumentace je užitečná pro zjišťování problémů s výkonem se problémy vstupně-výstupních operací, jako je využití disku.  
  
 Vytvoření instrumentované binární se [VInstr.exe](../profiling/vsinstr.md) nástroj. Po inicializaci profileru automaticky shromažďuje data z instrumentované binární soubory při spuštění cílová aplikace.  
  
 **Typ cílové aplikace**  
  
-   [Samostatné součásti rozhraní .NET framework](../profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Nativní samostatné součásti](../profiling/how-to-instrument-a-native-stand-alone-component-and-collect-timing-data-with-the-profiler-from-the-command-line.md)  
  
-   [Staticky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)  
  
-   [Dynamicky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)  
  
-   [Služby rozhraní .NET](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
-   [Nativní služby](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)  
  
## <a name="use-net-memory-methods-to-collect-memory-allocation-and-object-lifetime-data"></a>Pomocí metody paměti .NET ke shromažďování dat paměti přidělení a objekt doba platnosti  
 Metoda paměti .NET nástrojů pro profilaci umožňuje shromažďovat [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] dat přidělování paměti a informace o životnosti objektů v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Cílová aplikace můžete spustit pomocí profileru; můžete provést připojení profileru k spuštěnou instanci aplikace. a můžete vytvořit instrumentovaného verze této aplikace lze shromažďovat informace o podrobné časování společně s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] dat paměti.  
  
|Úloha|Typ cílové aplikace|  
|----------|-----------------------------|  
|**Spuštění aplikace**|-   [Samostatné aplikace rozhraní .NET Framework](../profiling/how-to-launch-a-stand-alone-dotnet-framework-application-with-the-profiler-to-collect-memory-data-by-using-the-command-line.md)|  
|**Připojit k spuštěných procesů**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-stand-alone-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [Webové aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|  
|**Moduly nástrojích**|-   [Samostatné součásti rozhraní .NET framework](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-memory-data.md)<br />-   [Staticky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)<br />-   [Dynamicky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
  
## <a name="use-the-concurrency-method-to-collect-resource-contention-and-thread-activity-data"></a>Metoda souběžného zpracování použít ke shromažďování data aktivity prostředků kolizí a přístup z více vláken  
 Metoda souběžného zpracování nástrojích pro profilaci umožňuje shromažďovat data aktivity přístup z více vláken a procesů a sporu prostředků z vícevláknové aplikace.  
  
 Aplikaci můžete spustit pomocí profileru, nebo můžete připojení profileru k spuštěnou instanci aplikace.  
  
|Úloha|Typ cílové aplikace|  
|----------|-----------------------------|  
|**Spuštění aplikace**|-   [Samostatné aplikace rozhraní .NET Framework](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)<br />-   [Samostatné nativní aplikace](../profiling/how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line.md)|  
|**Připojit k spuštěných procesů**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)<br />-   [Nativní samostatné aplikaci](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Webové aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Služba .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Nativní službě](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|  
  
## <a name="add-tier-interaction-data-to-a-profiling-run"></a>Přidání dat interakce vrstev pro spuštění profilování  
 Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci. V tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)  
  
## <a name="see-also"></a>Viz také:  
 [Profil samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)