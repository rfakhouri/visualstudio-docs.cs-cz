---
title: Řešení potíží při ladění snímků | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/07/2018
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b7916cbd3a7faa633baf53a18686779dc2b386c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857759"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Řešení potíží a známé problémy pro ladění snímků v sadě Visual Studio

Pokud problém nelze vyřešit pomocí postupu popsaného v tomto článku, obraťte se na snaphelp@microsoft.com.

## <a name="issue-snappoint-does-not-turn-on"></a>Problém: Snímkovací bod nezapne

Pokud se zobrazí výstražná ikona ![snímkovací bod výstražná ikona](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "snímkovací bod výstražná ikona") s vaší snímkovacích bodů namísto ikonu regulární snímkovací bod, pak snímkovací bod není zapnuté.

![Snímkovací bod nezapne](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "snímkovací bod nezapne")

Proveďte tyto kroky:

1. Ujistěte se, že máte stejnou verzi zdrojového kódu, který byl použit k vytvoření a nasazení vaší app.isua1. Ujistěte se, že se načítají správné symbolů pro vaše nasazení. Pokud chcete to provést, podívejte se **moduly** okno při ladění snímků a ověřit soubor symbolů sloupci zobrazí soubor .pdb načtené pro modul, který ladíte. Snapshot Debugger se pokusí automaticky stáhnout a použít symbolů pro vaše nasazení.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>Problém: Při otevření snímku se nenačtou symboly

Pokud se zobrazí následující okno, symboly se nenačetl.

![Symboly se nenačtou](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "symboly nenačtou.")

Proveďte tyto kroky:

- Klikněte na tlačítko **změnit nastavení symbolů...** odkaz na této stránce. V **ladění > symboly** nastavení, přidejte adresář mezipaměti symbolů. Restartujte ladění snímků po nastavení cesty k symbolu.

   Nasazení služby App Service musí odpovídat symboly nebo soubory PDB, k dispozici ve vašem projektu. Většině nasazeních (nasazení prostřednictvím sady Visual Studio, CI/CD s kanály Azure nebo Kudu, atd.) budou soubory symbolů podél publikovat do služby App Service. Adresář mezipaměti symbolů nastavení umožní sadě Visual Studio používat tyto symboly.

   ![Symbol nastavení](../debugger/media/snapshot-troubleshooting-symbol-settings.png "Symbol nastavení")

- Případně pokud vaše organizace používá server symbolů nebo sníží symboly v jinou cestu, použijte nastavení symbolu načtení správné symbolů pro vaše nasazení.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>Problém: Nejde zobrazit možnost "Připojit Snapshot Debugger" v Průzkumníkovi cloudu

Proveďte tyto kroky:

- Ujistěte se, že je nainstalovaná komponenta Snapshot Debugger. Otevřete instalační program sady Visual Studio a zkontrolujte **Snapshot Debugger** komponenta v úloze Azure.
::: moniker range="< vs-2019"
- Zajistěte, aby že vaše aplikace je podporovaná. V současné době pouze technologie ASP.NET (4.6.1+) a podporují aplikace ASP.NET Core (2.0 +) nasazené do služby Azure App Services.
::: moniker-end
::: moniker range=">= vs-2019"
- Ujistěte se, že se vaše aplikace podporuje:
  - Azure App Services - aplikací ASP.NET běžících na rozhraní .NET Framework 4.6.1 nebo novější.
  - Azure App Service – aplikace ASP.NET Core na .NET Core 2.0 nebo novější na Windows.
  - Virtuální počítače Azure (a škálovací sady virtuálních počítačů) - aplikací ASP.NET běžících na rozhraní .NET Framework 4.6.1 nebo novější.
  - Virtuální počítače Azure (a škálovací sady virtuálních počítačů) - aplikací ASP.NET Core na .NET Core 2.0 nebo novější na Windows.
  - Služby Azure Kubernetes – aplikace ASP.NET Core spuštěné v .NET Core 2.2 nebo vyšší na Debian 9.
  - Služby Azure Kubernetes – aplikace ASP.NET Core spuštěné v .NET Core 2.2 nebo vyšší na Alpine 3.8.
  - Služby Azure Kubernetes – aplikace ASP.NET Core spuštěné v .NET Core 2.2 nebo vyšší na Ubuntu 18.04.
::: moniker-end

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>Problém: Zobrazuje pouze omezená snímky v okně diagnostické nástroje

![Omezený snímkovací bod](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "omezený snímkovací bod")

Proveďte tyto kroky:

- Snímky spotřebovávat málo paměti, ale máte poplatek za potvrzení. Pokud ladicí program snímků zjistí, že je server v paměti v případě velkého zatížení, nepořizuje snímky. Zastavuje se relace ladicího programu snímků a zkusit to znovu, můžete odstranit již zachycené snímky.

## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>Problém: Ladění snímků s více verzemi nástroje Visual Studio, mi dává pocit chyby

VS 2019 vyžaduje novější verzi rozšíření pro Snapshot Debugger web ve službě Azure App Service.  Tato verze není kompatibilní s starší verze rozšíření pro Snapshot Debugger web používá sady VS 2017.  Pokud se pokusíte připojit Snapshot Debugger ve VS 2019 do služby Azure App Service, který byl dříve ladit pomocí ladicího programu snímků v sadě VS 2017 se zobrazí následující chyba:

![Nekompatibilní rozšíření webu pro Snapshot Debugger VS 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "rozšíření webu nekompatibilní Snapshot Debugger VS 2019")

Naopak pokud připojit Snapshot Debugger do Azure App Service, která byla dříve ladit pomocí ladicího programu snímků ve VS 2019 pomocí sady VS 2017, zobrazí se vám následující chybu:

![Nekompatibilní rozšíření webu pro Snapshot Debugger sady VS 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "rozšíření webu nekompatibilní Snapshot Debugger VS2017")

Chcete-li tento problém vyřešit, odstraňte následující nastavení aplikace na webu Azure Portal a znovu připojit Snapshot Debugger:

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>Problém: Mám potíže s ladění snímků a je potřeba povolit další protokolování

### <a name="enable-agent-logs"></a>Povolení protokolování agenta

Povolení a zakázání agenta protokolování otevřít Visual Studio přejděte do *nástroje > Možnosti > Snapshot Debugger > Povolit agenta protokolování*. Poznámka: Pokud *odstranit starý agent zaznamená při spuštění relace* je také povolena, každý úspěšné sady Visual Studio připojit se odstranit protokoly předchozích agenta.

Protokoly agenta najdete v následujících umístěních:

- App Services:
  - Přejděte na Web App Service Kudu (to znamená, yourappservice. **Správce řízení služeb**. azurewebsites.net) a přejděte do konzoly ladění.
  - Protokoly agenta se ukládají v následujícím adresáři:  D:\home\LogFiles\SiteExtensions\DiagnosticsAgentLogs\
- VM/VMSS:
  - Přihlaste se ke svému virtuálnímu počítači agenta, které protokoly se ukládají následujícím způsobem:  C:\WindowsAzure\Logs\Plugins\Microsoft.Azure.Diagnostics.IaaSDiagnostics\<Version>\SnapshotDebuggerAgent_*.txt
- AKS
  - Přejděte na následující adresář: / tmp/diag/AgentLogs / *

### <a name="enable-profilerinstrumentation-logs"></a>Povolení protokolů Profiler/instrumentace

Instrumentace protokoly najdete v následujících umístěních:

- App Services:
  - Protokolování chyb je automaticky odeslán do D:\Home\LogFiles\eventlog.xml, události jsou označené << název zprostředkovatele = "Instrumentace modul" / / >> nebo "Produkční zarážky"
- VM/VMSS:
  - Přihlaste se ke svému virtuálnímu počítači a otevřete Prohlížeč událostí.
  - Otevřete následujícím způsobem: *Protokoly Windows > aplikace*.
  - *Filtrovat aktuální protokol* podle *zdroj události* buď pomocí *produkční zarážky* nebo *instrumentace modul*.
- AKS
  - Instrumentace modul protokolování na /tmp/diag/log.txt (nastavit MicrosoftInstrumentationEngine_FileLogPath v souboru DockerFile)
  - Protokolování ProductionBreakpoint na /tmp/diag/shLog.txt

## <a name="known-issues"></a>Známé problémy

- Ladění snímků s více klienty sady Visual Studio na stejné služby App Service se momentálně nepodporuje.
- Optimalizace Roslyn IL nejsou plně podporovány v projektech ASP.NET Core. Pro některé projekty ASP.NET Core nebudete moci zobrazit některé proměnné nebo použití proměnných podmíněné příkazy.
- Speciální proměnné, jako například *$FUNCTION* nebo *$CALLER*, nelze vyhodnotit v podmíněné příkazy nebo protokolovací body pro projekty ASP.NET Core.
- Ladění snímků nefunguje v App Service, které mají [místní ukládání do mezipaměti](/azure/app-service/app-service-local-cache) zapnuté.
- Snímek ladění aplikace API se momentálně nepodporuje.

## <a name="site-extension-upgrade"></a>Upgrade rozšíření webu

Ladění snímků a Application Insights závisí na ICorProfiler, který načte do procesu lokality a způsobí, že soubor zamykání problémy při upgradu. Doporučujeme, abyste tento postup Ujistěte se, že neexistuje žádný dolů čas na produkční lokality.

- Vytvoření [Slot nasazení](/azure/app-service/web-sites-staged-publishing) ve službě App Service a nasaďte svůj web do slotu.
- Prohodit s produkčním slotu z Průzkumníku cloudu v sadě Visual Studio nebo z webu Azure portal.
- Zastavte Slot webu. Bude to trvat několik sekund ukončit vypnutí procesu w3wp.exe lokality ze všech instancí.
- Upgrade rozšíření webu slotu z webu kudu nebo na webu Azure portal (*okno App Service > vývojářské nástroje > Rozšíření > aktualizace*).
- Spusťte Slot webu. Doporučujeme navštívit web znovu zahřívání.
- Přepnout Slot s produkčním prostředí.

## <a name="see-also"></a>Viz také:

- [Ladění v sadě Visual Studio](../debugger/index.md)
- [Ladění živé aplikace v ASP.NET pomocí ladicího programu snímků](../debugger/debug-live-azure-applications.md)
- [Ladění za provozu technologie ASP.NET Azure virtuální Machines\Virtual počítače Škálovací sady pomocí ladicího programu snímků](../debugger/debug-live-azure-virtual-machines.md)
- [Ladění za provozu technologie ASP.NET Kubernetes se službou Azure pomocí ladicího programu snímků](../debugger/debug-live-azure-kubernetes.md)
- [Nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md)