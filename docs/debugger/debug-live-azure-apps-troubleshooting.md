---
title: Řešení potíží při ladění snímků | Dokumentace Microsoftu
ms.custom: ''
ms.date: 04/24/2019
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3c66ba4a5031326ec288d3a5f2f3c4851d17ca6
ms.sourcegitcommit: 74c5360186731de07828764eb32ea1033a8c2275
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559767"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Řešení potíží a známé problémy pro ladění snímků v sadě Visual Studio

Pokud problém nelze vyřešit pomocí postupu popsaného v tomto článku, vyhledejte problém na [komunity vývojářů](https://developercommunity.visualstudio.com/spaces/8/index.html) nebo ohlásit nový problém výběrem **pomáhají** > **odeslat zpětnou vazbu**   >  **Nahlásit problém** v sadě Visual Studio.

## <a name="issue-attach-snapshot-debugger-encounters-an-http-status-code-error"></a>Problém: "Připojit Snapshot Debugger" dojde k chybě kód stavu HTTP

Pokud se zobrazí následující chyba v **výstup** okno při pokusu o připojení, může být známý problém, níže uvedené. Vyzkoušejte navrhované řešení a pokud problém nezmizí, kontaktujte před alias.

`[TIMESTAMP] Error --- Unable to Start Snapshot Debugger - Attach Snapshot Debugger failed: System.Net.WebException: The remote server returned an error: (###) XXXXXX`

### <a name="401-unauthorized"></a>Neautorizováno (401)

Tato chyba označuje, že volání REST vydala Visual Studio na Azure používá neplatné přihlašovací údaje. O známý problém s modulem Azure Active Directory snadno OAuth může vést k této chybě.

Proveďte tyto kroky:

* Ujistěte se, že váš účet přizpůsobení sady Visual Studio má oprávnění k předplatnému Azure a prostředek, který při připojování k. Rychlý způsob, jak zjistit se to je zkontrolovat, zda daný prostředek k dispozici v dialogovém okně z **ladění** > **připojit Snapshot Debugger...**   >  **Prostředků azure** > **vybrat existující**, nebo v Průzkumníku cloudu.
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

### <a name="403-forbidden"></a>Zakázáno (403)

Tato chyba označuje, že bylo odepřeno oprávnění. Příčinou může být mnoho různých problémů.

Proveďte tyto kroky:

* Ověřte, že váš účet Visual Studio má platné předplatné Azure s potřebnými oprávněními řízení přístupu na základě Role (RBAC) pro prostředek. Pro App Service, zaškrtněte, pokud máte oprávnění k [dotazu](https://docs.microsoft.com/rest/api/appservice/appserviceplans/get) plánu služby App Service hostují vaši aplikaci.
* Ověřte, že časové razítko ze svého klientského počítače je správné a aktuální. Servery s časovými razítky vypnout pomocí více než 15 minut od časové razítko požadavku obvykle vytvoří tuto chybu.
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

### <a name="404-not-found"></a>(404) nebyl nalezen

Tato chyba označuje, že web se nenašel na serveru.

Proveďte tyto kroky:

* Ověřte, že máte nasazené a běží na prostředek služby App Service, který se připojuje k webu.
* Ověřte, že lokalita je k dispozici na https://\<prostředků\>. azurewebsites.net
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

### <a name="406-not-acceptable"></a>(406) nepřijatelný

Tato chyba označuje, že je schopna odpovědět na typ nastavený v hlavičce Accept požadavku na server.

Proveďte tyto kroky:

* Ověřte, že je web dostupný na https://\<prostředků\>. azurewebsites.net
* Ověřte, jestli váš web nebyl migrován do nové instance. Snapshot Debugger pojem ARRAffinity používá pro směrování žádostí na konkrétní instance, které mohou způsobit přerušovaně k této chybě.
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

### <a name="409-conflict"></a>Konflikt (409)

Tato chyba označuje, že žádost je v konfliktu s aktuálním stavem serveru.

Jde o známý problém, ke které dochází, když se uživatel pokusí připojit Snapshot Debugger pro služby App Service, která povolila aplikaci ApplicationInsights. ApplicationInsights nastaví AppSettings s jinou velikostí písmen než Visual Studio, příčinou tohoto problému.

::: moniker range=">= vs-2019"
Můžeme to byly vyřešeny v aplikaci Visual Studio 2019.
::: moniker-end

Proveďte tyto kroky:

::: moniker range="vs-2017"

* Na webu Azure Portal ověřte, že AppSettings pro ladicího programu snímků (SNAPSHOTDEBUGGER_EXTENSION_VERSION) a InstrumentationEngine (INSTRUMENTATIONENGINE_EXTENSION_VERSION) jsou velká písmena. Pokud ne, aktualizujte nastavení ručně, což vynutí restartování serveru.
::: moniker-end
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

### <a name="500-internal-server-error"></a>Interní chybu serveru (500)

Tato chyba označuje, že web je úplně vypnutý nebo server nemůže zpracovat požadavek. Funkce pouze snímku ladicí program ke spuštění aplikace. [Application Insights Snapshot debuggeru](https://docs.microsoft.com/azure/azure-monitor/app/snapshot-debugger) poskytuje snímkování na výjimkách a může být vždycky ten nejlepší nástroj pro vaše potřeby.

### <a name="502-bad-gateway"></a>Chybná brána (502)

Tato chyba označuje síťové potíže na straně serveru a může být dočasné.

Proveďte tyto kroky:

* Počkejte několik minut, než Snapshot Debugger připojit znovu.
* Pokud k této chybě nezmizí, použijte jednu z kanálech zpětné vazby, které jsou popsané na začátku tohoto článku.

## <a name="issue-snappoint-does-not-turn-on"></a>Problém: Snímkovací bod nezapne

Pokud se zobrazí výstražná ikona ![snímkovací bod výstražná ikona](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "snímkovací bod výstražná ikona") s vaší snímkovacích bodů namísto ikonu regulární snímkovací bod, pak snímkovací bod není zapnuté.

![Snímkovací bod nezapne](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "snímkovací bod nezapne")

Proveďte tyto kroky:

1. Ujistěte se, že máte stejnou verzi zdrojového kódu, který se používá k vytvoření a nasazení vaší aplikace. Ujistěte se, že se načítají správné symbolů pro vaše nasazení. Pokud chcete to provést, podívejte se **moduly** okno při ladění snímků a ověřit soubor symbolů sloupci zobrazí soubor .pdb načtené pro modul, který ladíte. Snapshot Debugger se pokusí automaticky stáhnout a použít symbolů pro vaše nasazení.

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

::: moniker range=">= vs-2019"
## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>Problém: Ladění snímků s více verzemi nástroje Visual Studio, mi dává pocit chyby

Visual Studio 2019 vyžaduje novější verzi rozšíření pro Snapshot Debugger web ve službě Azure App Service.  Tato verze není kompatibilní s starší verze rozšíření pro Snapshot Debugger web používá Visual Studio 2017.  Pokud se pokusíte připojit Snapshot Debugger v aplikaci Visual Studio 2019 do služby Azure App Service, který byl dříve ladit pomocí ladicího programu snímků v sadě Visual Studio 2017 se zobrazí následující chyba:

![Nekompatibilní rozšíření webu pro Snapshot Debugger Visual Studio 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "rozšíření webu nekompatibilní Snapshot Debugger. 2019 Visual Studio")

Naopak pokud připojit Snapshot Debugger do Azure App Service, která byla dříve ladit pomocí ladicího programu snímků ve Visual Studio 2019 pomocí sady Visual Studio 2017, zobrazí se vám chybová zpráva:

![Nekompatibilní rozšíření webu pro Snapshot Debugger Visual Studio 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "nekompatibilní Snapshot Debugger web rozšíření sady Visual Studio 2017")

Chcete-li tento problém vyřešit, odstraňte následující nastavení aplikace na webu Azure Portal a znovu připojit Snapshot Debugger:

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION
::: moniker-end

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
  - Protokolování chyb je automaticky odeslán do D:\Home\LogFiles\eventlog.xml, události jsou označené `<Provider Name="Instrumentation Engine" />` nebo "Produkční zarážky"
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
