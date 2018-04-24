---
title: 'Postupy: instrumentace nativní služby a shromažďování podrobných dat časování pomocí příkazového řádku profileru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: dfe58b39-63f8-4a87-ab3a-2b5b14faa8d0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 9dcd4052078a3a7327b0a48fca8812a2d5393917
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line"></a>Postupy: Instrumentace nativní služby a shromažďování podrobných dat časování pomocí příkazového řádku profileru
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje příkazového řádku v nástrojích pro profilaci k instrumentaci nativní (C/C++) služby a shromažďování podrobných dat časování.  
  
> [!NOTE]
>  Pomocí metody instrumentace nelze profilu služby, pokud nelze restartovat službu po spuštění počítače, tato služba, která spustit pouze v případě, že operační systém při spuštění.  
>   
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. V 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Shromažďování podrobných dat časování pomocí metody instrumentace z nativní službě, můžete použít [VSInstr.exe](../profiling/vsinstr.md) nástroj pro generování instrumentovaného verzi komponentu. Je pak nahradit verzi služby-instrumentovány instrumentovaného verze, a ujistěte se, že služba je nakonfigurována pro spustit ručně. Potom je nutné spustit profileru.  
  
 Když je služba spuštěna, časování data jsou shromažďována automaticky do datového souboru. Můžete pozastavit a obnovit shromažďování dat během relace profilování.  
  
 K ukončení relace profilování, vypněte službu a poté explicitně vypněte profileru.  
  
## <a name="starting-the-application-with-the-profiler"></a>Spouštění aplikace s Profilerem  
  
#### <a name="to-start-profiling-a-native-service"></a>Ke spuštění profilování nativní službě  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Použití **vsinstr –** nástroj pro generování instrumentovaného verzi binární.  
  
3.  Nahradíte původní binární instrumentovaného verzí. Ve správci řízení služby systému Windows Ujistěte se, že služba typ spuštění nastavený na ruční.  
  
4.  Spusťte profileru. Typ:  
  
     **VSPerfCmd** [/start](../profiling/start.md) **: trasování**[/výstup](../profiling/output.md) **:** `OutputFile` [`Options`]    
  
    -   **/Start:trace** možnost inicializuje profileru.  
  
    -   **/Výstup:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:trace** možnost.  
  
    > [!NOTE]
    >  **User** a **/crosssession** možnosti jsou obvykle vyžaduje pro aplikace ASP.NET.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje, doména a uživatelské jméno účtu, který vlastní pracovní proces ASP.NET. Tato možnost je povinná, pokud je proces spuštěný jako uživatel, než je přihlášený uživatel. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. Tato možnost je povinná, pokud je spuštěná aplikace ASP.NET v jiné relaci. Id relace je uvedena ve sloupci ID relace na kartě procesy ve Správci úloh systému Windows. **/CS** lze zadat jako zkratkou pro **/crosssession**.|  
    |[/waitstart](../profiling/waitstart.md)[**:**`Interval`]|Určuje počet sekund pro čekání profileru k chybě při inicializaci předtím, než vrátí chybu. Pokud `Interval` není zadán, profileru čeká neomezenou dobu zaseknout. Ve výchozím nastavení **/start** vrátí okamžitě.|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|Spuštění profileru se shromažďování dat pozastavena, přidejte **/globaloff** možnost k **/start** příkazového řádku. Použití **/globalon** obnovit profilace.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Shromažďuje informace z čítače zadaný v konfiguračním výkon procesoru. Informace o čítači se přidá na data shromažďovaná v každé profilování události.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
5.  Spusťte službu ze Správce řízení služeb.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud je služba spuštěná, můžete použít **VSPerfCmd.exe** možnosti spuštění a zastavení zápisu dat do datového souboru profileru. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, například spuštění nebo vypnutí služby.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující dvojice **VSPerfCmd** možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces zadaný pomocí ID procesu (`PID`).|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|Spustí (**/threadon**) nebo zastaví (**/threadoff**) shromažďování dat pro vlákno určeného ID vlákna (`TID`).|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, zastavte službu, která běží komponentu instrumentované a pak zavolají **VSPerfCmd**[/Shutdown](../profiling/shutdown.md) možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Zastavte službu ze Správce řízení služeb.  
  
2.  Vypněte profileru. Typ:  
  
     **Vsperfcmd – Shutdown**  
  
3.  Modul instrumentovaného nahraďte původní. V případě potřeby znovu nakonfigurujte typ spouštění služby.  
  
## <a name="see-also"></a>Viz také  
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)   
 [Zobrazení dat metody instrumentace](../profiling/instrumentation-method-data-views.md)