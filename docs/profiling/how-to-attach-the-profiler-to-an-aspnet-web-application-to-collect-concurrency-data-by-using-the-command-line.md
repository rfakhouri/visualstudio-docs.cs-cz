---
title: 'Postupy: připojení profileru k webové aplikaci ASP.NET ke shromažďování dat souběžnosti pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0e215fdd-55f8-43ef-9534-06542eefe223
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 09ba7884d9c8bd1abf9762046b9e8f7fb534d530
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766006"
---
# <a name="how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line"></a>Postupy: připojení profileru k webové aplikaci ASP.NET ke shromažďování dat souběžnosti pomocí příkazového řádku
Tento článek popisuje způsob použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k aplikaci ASP.NET a shromažďování dat souběžnosti proces a přístup z více vláken.  
  
 Nástroje příkazového řádku nástroje profilace jsou umístěné v *\Team Tools\Performance nástroje* podadresáři instalačního adresáře nástroje Visual Studio. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Použití profileru na příkazovém řádku, je nutné přidat cestu nástroje do proměnné prostředí PATH z **příkazového řádku** okno, nebo přidejte k příkazu sám sebe. Další informace najdete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Ke shromažďování dat souběžnosti, připojení profileru k pracovního procesu ASP.NET, který je hostitelem webové stránky. Při profileru je připojen k aplikaci, můžete pozastavit a obnovit data kolekce. K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté. Ve většině případů byste měli vymazat na konci relace profilování proměnné prostředí.  
  
## <a name="attach-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-a-aspnet-application"></a>Chcete-li připojení profileru k aplikaci ASP.NET  
  
1.  Spusťte profileru zadáte následující příkaz:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md) možnost inicializuje profileru ke shromažďování dat kolizí prostředku.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Jakákoliv možnost, můžete použít v následující tabulce se **/start** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain\`]`UserName`|Určuje nepovinné domény a uživatelské jméno účtu, který chcete povolit přístup k profileru.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v samostatné (. *ETL*) souboru.|  
  
2.  Spuštění aplikace ASP.NET v obvyklým způsobem.  
  
3.  Připojení profileru k pracovního procesu ASP.NET tak, že zadáte následující příkaz:**VSPerfCmd / připojit:** `PID` [**/targetclr:**`Version`]  
  
    -   `PID` Určuje ID nebo názvem pracovního procesu technologie ASP.NET. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci. Tento parametr je volitelný.  
  
## <a name="control-data-collection"></a>Řízení shromažďování dat  
 Když aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do souboru pomocí *VSPerfCmd.exe* možnosti. Pomocí řízení shromažďování dat můžete shromažďování dat pro konkrétní součást spuštění programu, jako je například počáteční nebo vypnutí aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Dvojice VSPerfCmd možnosti uvedené v následující tabulce spustit a zastavit shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, ID procesu (`PID`) určuje.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, ID procesu (`PID`) nebo název procesu (*Nazev_procedury*) určuje. **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán žádný proces.|  
  
## <a name="end-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, nesmí být profileru shromažďování dat. Můžete zastavit shromažďování dat z aplikace, která je profilovaným s metoda souběžného zpracování restartováním pracovního procesu technologie ASP.NET nebo vyvoláním **VSPerfCmd / detach** možnost. Potom vyvolat **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – /globaloff** příkaz vymaže profilování proměnné prostředí, ale konfigurace systému není resetovat, dokud se počítač restartuje.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Odpojte profileru z cílová aplikace ukončením ho nebo pomocí následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd / odpojit**  
  
2.  Vypněte profileru zadáním následujícího příkazu na příkazovém řádku:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
## <a name="see-also"></a>Viz také:  
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Rychlé profilování webových stránek pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md)