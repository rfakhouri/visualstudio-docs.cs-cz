---
title: 'Postupy: připojení profileru k nativní službě ke shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 283a1ee1-b43e-4daf-95ae-1311925a42a8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 00fa570597bca0a7a5d80c7871f53c6c555dc856
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: Připojení profileru k nativní službě ke shromažďování dat souběžnosti pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k nativní (C/C++) služby a shromažďování dat souběžnosti proces a vlákno pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
> [!NOTE]
>  Nástroje příkazového řádku balíku nástrojů pro profilaci jsou umístěny v podadresáři \Team Tools\Performance Tools instalačního adresáře sady Visual Studio. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Použití profileru na příkazovém řádku, je nutné přidat cestu nástroje do proměnné prostředí PATH z **příkazového řádku** okno nebo do příkazu sám sebe. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Při profileru je připojen ke službě, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru ke službě a profileru musí být explicitně vypnuté.  
  
## <a name="attaching-the-profiler"></a>Připojení profileru  
 K připojení profileru k nativní službě, můžete použít **VSPerfCmd od počátku** a **/ připojit** možnosti inicializovat profileru a jeho připojení k cílové aplikaci. Můžete zadat **/start** a **/ připojit** a jejich odpovídající možnosti na jednoho příkazového řádku. Můžete také přidat **/globaloff** možnost pozastavit shromažďování dat na začátku cílová aplikace. Pak použijete **/globalon** zahájíte shromažďovat data.  
  
#### <a name="to-attach-the-profiler-to-a-native-service"></a>Chcete-li připojení profileru k nativní službě  
  
1.  Pokud služba není spuštěná, spusťte službu.  
  
2.  Zadáním následujícího příkazu na příkazovém řádku spusťte profileru:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency output:** `OutputFile` [`Options`]  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Jakákoliv možnost, můžete použít v následující tabulce se **/start** možnost.  
  
    > [!NOTE]
    >  Většina služeb vyžadují **User** a **/crosssession** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`UserName`|Určuje nepovinné domény a uživatelské jméno účtu, který chcete povolit přístup k profileru.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
3.  Připojení profileru ke službě zadáním následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd / připojení:** `PID`  
  
     `PID` Určuje ID procesu nebo název procesu cílové aplikace. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru s možností VSPerfCmd.exe. Pomocí řízení shromažďování dat můžete shromažďování dat pro konkrétní součást spuštění programu, jako je například počáteční nebo vypnutí aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Dvojice možnosti uvedené v následující tabulce spustit a zastavit shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, ID procesu (`PID`) určuje.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, ID procesu (`PID`) nebo název procesu (*Nazev_procedury*) určuje. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán žádný proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat z nativní služby, která je profilovaným s metoda souběžného zpracování Probíhá zastavování služby nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Odpojte profileru z cílová aplikace Probíhá zastavování služby nebo zadáním následujícího příkazu na příkazovém řádku:  
  
     Typ **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru zadáním následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)