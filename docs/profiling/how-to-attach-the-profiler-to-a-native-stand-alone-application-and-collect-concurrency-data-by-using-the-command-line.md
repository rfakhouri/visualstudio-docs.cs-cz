---
title: 'Postupy: připojení profileru k nativní samostatné aplikaci a shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 12d3e0f3-4b74-4e66-8fbf-8ac99bd4f91c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: e3d74821cabbd6fa4c3a950d14a71f8eff73c36f
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34766585"
---
# <a name="how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-concurrency-data-by-using-the-command-line"></a>Postupy: připojení profileru k nativní samostatné aplikaci a shromažďování dat souběžnosti pomocí příkazového řádku
Tento článek popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vláken nástroje příkazového řádku v nástrojích pro profilaci připojení profileru k nativní spuštění samostatné aplikace (C/C++) a shromažďovat data kolizí.  
  
> [!NOTE]
>  Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři instalačního adresáře nástroje Visual Studio. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, je nutné přidat cestu nástroje do proměnné prostředí PATH z **příkazového řádku** okno nebo ho přidat do samotný příkaz. Další informace najdete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté.  
  
## <a name="attach-the-profiler-to-a-running-native-application"></a>Připojení profileru ke spuštění nativní aplikace  
  
#### <a name="to-attach-the-profiler-to-a-running-native-application"></a>Chcete-li připojení profileru ke spuštění nativní aplikace  
  
1.  Na příkazovém řádku zadejte následující příkaz:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency**  
  
     V následující tabulce se můžete použít některou z možností **/start:concurrency**možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`Username`|Určuje nepovinné domény a uživatelské jméno účtu, který chcete povolit přístup k profileru.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
2.  Připojení profileru k cílové aplikaci tak, že zadáte následující příkaz:  
  
     **VSPerfCmd**[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`}  
  
     `PID` Určuje ID procesu cílová aplikace. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
## <a name="control-data-collection"></a>Řízení shromažďování dat  
 Když cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí *VSPerfCmd.exe* možnosti. Pomocí řízení shromažďování dat můžete shromažďování dat pro konkrétní součást spuštění programu, jako je například počáteční nebo vypnutí aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Dvojice možnosti uvedené v následující tabulce spustit a zastavit shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, ID procesu (`PID`) určuje.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, ID procesu (`PID`) nebo název procesu (*Nazev_procedury*) určuje. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán žádný proces.|  
  
## <a name="end-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat z aplikace, která je profilovaným pomocí metody vzorkování ukončením aplikace nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Odpojte z cílová aplikace profileru zavřením nebo zadáním následujícího příkazu:  
  
     **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru tak, že zadáte následující příkaz:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)