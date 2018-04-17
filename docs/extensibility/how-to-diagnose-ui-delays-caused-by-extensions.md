---
title: Diagnostikování rozšíření uživatelského rozhraní se zpozdí v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
author: PooyaZv
ms.author: pozandev
manager: douge
ms.workload: multiple
ms.openlocfilehash: b63f9538c916b74874031704a1f60d0646f8d032
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-diagnose-ui-delays-caused-by-extensions"></a>Postupy: diagnostikování uživatelského rozhraní zpoždění způsobené rozšíření

Když uživatelského rozhraní přestane reagovat, Visual Studio prověří zásobníku volání z vlákna uživatelského rozhraní, počínaje listu a směřování základní. Pokud Visual Studio zjistí, že rámce zásobníku volání patří do modul, který je součástí nainstalované a povolené rozšíření, zobrazí oznámení.

![Zpoždění uživatelského rozhraní (absence reagování) oznámení](media/ui-delay-notification-in-vs.png)

Oznámení informuje uživatele, že může být zpoždění uživatelského rozhraní (tj. absence reagování v uživatelském rozhraní) byla výsledek kód z rozšíření. Také poskytuje uživateli s možností zakázat rozšíření nebo budoucí oznámení pro tuto příponu.

Tento dokument popisuje, jak diagnostikovat, co ve vašem kódu rozšíření je příčinou oznámení zpoždění uživatelského rozhraní. 

> [!NOTE]
> Nepoužívejte instanci experimentální sady Visual Studio k diagnostikování uživatelské rozhraní se zpozdí. Některé části zásobníku volání analýzy požadované pro oznámení zpoždění uživatelského rozhraní nejsou k dispozici při použití experimentální instance, což znamená, že nemusí být zobrazeny oznámení zpoždění uživatelského rozhraní.

Přehled diagnostiky procesu vypadá takto:
1. Identifikujte scénář aktivační události.
2. Pomocí aktivity protokolování restartujte VS.
3. Spusťte trasování událostí pro Windows.
4. Oznámení se objeví znovu aktivovat.
5. Zastavte trasování událostí pro Windows.
6. Zkontrolujte protokol aktivity získat ID zpoždění.
7. Analýza trasování událostí pro Windows trasování pomocí ID zpoždění v kroku 6.

V následujících částech provedeme tyto kroky podrobněji.

## <a name="identifying-the-trigger-scenario"></a>Identifikace scénáře aktivace

Při diagnostice ke zpoždění uživatelského rozhraní, musíte nejdřív určit, jaké (posloupnost akcí) způsobí, že chcete zobrazit oznámení Visual Studio. Toto je, aby pro vás moct později aktivovat oznámení s zapnout protokolování.

## <a name="restarting-vs-with-activity-logging-on"></a>Restartování VS s aktivitou přihlašování

Visual Studio může generovat protokol"aktivity" poskytující informace, které jsou užitečné při ladění problém. Chcete-li aktivita protokolování v sadě Visual Studio, spuštění sady Visual Studio s `/log` možnost příkazového řádku. Po spuštění sady Visual Studio, protokol aktivit se ukládají v následujícím umístění:

```DOS
%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml
```

Další informace o tom, jak můžete najít váš VS ID instance najdete v tématu [nástroje pro zjišťování a správu instancí sady Visual Studio](../install/tools-for-managing-visual-studio-instances.md). Budeme později používat tento protokol aktivit a zjistěte další informace o uživatelské rozhraní se zpozdí a související oznámení.

## <a name="starting-etw-tracing"></a>Výchozí trasování událostí pro Windows

Můžete použít [nástroje PerfView](https://github.com/Microsoft/perfview/) ke shromažďování při trasování ETW. Nástroje PerfView poskytuje snadno použitelné rozhraní pro shromažďování při trasování ETW i pro analýzu ho. Chcete-li shromažďovat trasování, použijte následující příkaz:

```DOS
Perfview.exe collect C:\trace.etl /BufferSizeMB=1024 -CircularMB:2048 -Merge:true -Providers:*Microsoft-VisualStudio:@StacksEnabled=true -NoV2Rundown /kernelEvents=default+FileIOInit+ContextSwitch+Dispatcher
```

To umožňuje "Microsoft Visual Studio" poskytovatele, který se zprostředkovatel, který Visual Studio použije pro události související s oznámení zpoždění uživatelského rozhraní. Určuje také klíčové slovo jádra zprostředkovatele, který můžete vygenerovat "Zásobníky vlákna čas" zobrazení pomocí nástroje PerfView.

## <a name="triggering-the-notification-to-appear-again"></a>Oznámení se objeví znovu aktivován

Po nástroje PerfView bylo zahájeno trasování kolekce, můžete pořadí akce aktivační události (z kroku 1) pro oznámení se objeví znovu. Jakmile se zobrazí oznámení, můžete zastavit kolekce trasování nástroje PerfView ke zpracování a vygenerovat výstupní soubor trasování.

## <a name="stopping-etw-tracing"></a>Zastavit trasování událostí pro Windows

Chcete-li zastavit shromažďování trasování, jednoduše použijte `Stop collection` tlačítka v okně nástroje PerfView. Po zastavení shromažďování trasování nástroje PerfView bude automaticky zpracovávat události trasování událostí a vygeneruje soubor výstup trasování.

## <a name="examining-the-activity-log-to-get-the-delay-id"></a>Aktivity protokolu získat ID zpoždění

Jak už bylo zmíněno dříve, můžete najít v protokolu aktivit `%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml`. Pokaždé, když Visual Studio zjistí rozšíření zpoždění uživatelského rozhraní, zapíše do protokolu činnosti s uzlem `UIDelayNotifications` jako zdroj. Tento uzel obsahuje čtyři údaje o zpoždění uživatelského rozhraní:

- ID zpoždění uživatelského rozhraní, pořadové číslo, které jednoznačně identifikuje ke zpoždění uživatelského rozhraní v relaci VS
- ID relace, které je jedinečným identifikátorem od začátku až do zavřete relaci sady Visual Studio
- Zda se zobrazí oznámení zpoždění uživatelského rozhraní
- Rozšíření, které pravděpodobně nezdařila z důvodu zpoždění uživatelského rozhraní

```xml
<entry>
  <record>271</record>
  <time>2018/02/03 12:02:52.867</time>
  <type>Information</type>
  <source>UIDelayNotifications</source>
  <description>A UI delay (Delay ID = 0) has been detected. (Session ID=16e49d4b-26c2-4247-ad1c-488edeb185e0; Blamed extension="UIDelayR2"; Notification shown? Yes.)</description>
</entry>
```

> [!NOTE]
> Ne všechny uživatelské rozhraní se zpozdí za následek oznámení. Proto byste měli vždy zkontrolovat "Oznámení zobrazí?" hodnota správně určit správné zpoždění uživatelského rozhraní.

Po nalezení správné zpoždění uživatelského rozhraní v protokolu aktivit, poznamenejte si ID zpoždění uživatelského rozhraní, zadané v uzlu. ID budete používat k vyhledejte odpovídající události trasování událostí pro Windows v dalším kroku.

## <a name="analyzing-the-etw-trace"></a>Analýza trasování ETW

Dále otevřete v trasovacím souboru. To provedete pomocí stejné instance nástroje PerfView nebo spouští novou instanci a nastavení aktuální cesta ke složce v levém horním okna do umístění souboru trasování.

![Nastavení cesty ke složce v nástroje Perfview](media/perfview-set-path.png)

Potom vyberte soubor trasování v levém podokně a otevřete ho v nabídce klikněte pravým tlačítkem nebo kontextu zvolíte otevřete.

> [!NOTE]
> Ve výchozím nastavení nástroje PerfView výstupu archivu. Při otevření trace.zip automaticky dekomprimuje archivu a otevře trasování. Můžete ji přeskočit zrušením zaškrtnutí políčka "Zip" během trasování kolekce. Ale pokud máte v úmyslu přenosu a použít trasování v různých počítačích, důrazně doporučujeme před zrušíte zaškrtnutí "Zip". Bez této možnosti vyžaduje PDB pro sestavení Ngen nebude doprovázet trasování a proto nebudou rozpoznány symboly ze sestavení Ngen na cílovém počítači. (Viz [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/devops/2012/12/10/creating-ngen-pdbs-for-profiling-reports/) Další informace o soubory PDB pro Ngen sestavení.) 

Ho může trvat několik minut, než nástroje PerfView ke zpracování a otevřete trasování. Po trasování je otevřené, zobrazí se seznam různých "zobrazení" v něm.

![Zobrazení se souhrnnými informacemi trasování nástroje PerfView](media/perfview-summary-view-events-selected.png)

Zobrazení "Události" nejprve použijeme k získání časové rozmezí zpoždění uživatelského rozhraní:

1. Otevření zobrazení "Události" výběrem uzlu "Události" v části trasování a zvolením otevřete z nabídky klikněte pravým tlačítkem nebo kontextu.
2. Vyberte "`Microsoft-VisualStudio/ExtensionUIUnresponsiveness`" v levém podokně.
3. Stiskněte klávesu Enter

Výběr platí a všechny `ExtensionUIUnresponsiveness` události se zobrazí v pravém podokně.

![Výběr události v zobrazení událostí](media/perfview-event-selection.png)

Každý řádek v pravém podokně odpovídá ke zpoždění uživatelského rozhraní. Události obsahuje hodnotu "Zpoždění ID", který se má shodovat s ID zpoždění v protokolu aktivit v kroku 6. Protože `ExtensionUIUnresponsiveness` je spouštěna na konci zpoždění uživatelského rozhraní, časové razítko události (přibližně) značky koncový čas zpoždění uživatelského rozhraní. Události také obsahuje dobu trvání zpoždění. Jsme lze odečíst jeho trvání časové razítko konce získat časové razítko při spuštění zpoždění uživatelského rozhraní.

![Výpočet uživatelského rozhraní zpoždění období](media/ui-delay-time-range.png)

V předchozím snímku obrazovky například časové razítko události je 12,125.679 a doba trvání zpoždění je 6,143.085 (ms). Tedy,
* Zpoždění spuštění je 12,125.679 6,143.085 = 5,982.594.
* Časové rozmezí zpoždění uživatelského rozhraní je 5,982.594 k 12,125.679.

Jakmile máme časové rozmezí, jsme zavřete mimo zobrazení událostí a otevřete zobrazení "Zásobníky vlákna čas (s aktivitami StartStop)". Toto zobrazení je obzvláště užitečné, protože často rozšíření, která blokují vlákna uživatelského rozhraní jsou jenom čekání na operaci I/čítači nebo jiná vlákna. "Procesoru zásobníku" zobrazení, které je možností přejít k většině případů, nemusí proto zachytit času stráví vlákno blokování vzhledem k tomu nepoužívá procesoru během této doby. "Vláken čas zásobníky" řeší tento problém tím správně zobrazující blokované čas.

![Uzel zásobníky čas (s aktivitami StartStop) vlákna v zobrazení souhrnu nástroje PerfView](media/perfview-thread-time-with-startstop-activities-stacks.png)

Při otevírání "Zásobníky vlákna čas" zobrazení, vyberte "devenv" proces zahájíte analýzu.

![Zobrazení času zásobníky pro analýzu zpoždění uživatelského rozhraní vláknu](media/ui-delay-thread-time-stacks.png)

V zobrazení "Zásobníky vlákna čas" v levé horní části stránky, můžete nastavit časové rozmezí na hodnoty, které jsme počítá v předchozím kroku a stiskněte klávesu Enter, tak zásobníky upraveny tak, aby tento časový rozsah.

> [!NOTE]
> Při zjišťování, které vlákna uživatelského rozhraní lze neintuitivní, pokud kolekce trasování spustí po Visual Studio je již otevřeno vlákno (spuštění). První elementy v zásobníku vlákna uživatelského rozhraní (spouštění) jsou však nejpravděpodobnější vždy DLL operačního systému (ntdll.dll a kernel32.dll) následuje devenv!? a pak msenv!?. Toto pořadí může pomoci identifikovat vlákna uživatelského rozhraní.

 ![Identifikace spuštění vlákna](media/ui-delay-startup-thread.png)

Toto zobrazení můžete také dál filtrovat podle pouze včetně balíčcích, které obsahují moduly ze svého balíčku.

* "GroupPats" nastaven na prázdný text k odebrání všech seskupení přidán ve výchozím nastavení.
* Sada "IncPats" zahrnout část název sestavení kromě existující proces filtru. V takovém případě je nutné "devenv; UIDelayR2 ".

![Nastavení GroupPath a IncPath v zobrazení času zásobníky vlákna](media/perfview-tts-group-path-inc-path.png)

Nástroje PerfView obsahuje podrobné pokyny v nabídce Nápověda, který můžete použít k identifikaci kritické body v kódu. Kromě toho následující odkazy obsahují další informace o tom, jak využívat Visual Studio dělení na vlákna rozhraní API za účelem optimalizace kódu:

* [https://aka.ms/vsthreading](https://aka.ms/vsthreading)
* [https://aka.ms/vsthreadingcookbook](https://aka.ms/vsthreadingcookbook)

Můžete použít také novou statickou analyzátorů Visual Studio pro rozšíření (balíček NuGet [sem](https://www.nuget.org/packages/microsoft.visualstudio.sdk.analyzers)), které poskytují pokyny na osvědčené postupy pro psaní efektivní rozšíření. Podívejte se do seznamu [VS SDK analyzátorů](https://github.com/Microsoft/VSSDK-Analyzers/blob/master/doc/index.md) a [dělení na vlákna analyzátorů](https://github.com/Microsoft/vs-threading/blob/master/doc/analyzers/index.md).

> [!NOTE]
> Pokud nelze vyřešit absence reagování z důvodu závislosti nemáte řízení přes (například pokud vaše rozšíření má volat synchronní VS služby ve vlákně UI), bychom rádi vědět o něm. Pokud jste členem naší program Visual Studio partnera, kontaktujte nás odesláním žádosti o podporu developer. Jinak hodnota pomocí nástroje "nahlásit problém, odešlete svůj názor a zahrnují `"Extension UI Delay Notifications"` v názvu. Uveďte také podrobný popis analýzy.
