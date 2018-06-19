---
title: 'Postupy: diagnostikování rozšíření výkonu | Microsoft Docs'
ms.custom: ''
ms.date: 11/08/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 46b0a1e3-7e69-47c9-9d8d-a1815d6c3896
author: BertanAygun
ms.author: bertaygu
manager: douge
ms.workload:
- bertaygu
ms.openlocfilehash: 60a7d1c3178d0fd74983d3f1096d01e578a49a00
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133262"
---
# <a name="measuring-extension-impact-in-startup"></a>Měření rozšíření dopad na spuštění

## <a name="focus-on-extension-performance-in-visual-studio-2017"></a>Zaměřit se na výkon rozšíření v Visual Studio 2017

Na základě názorů zákazníků, jeden z konkrétní oblasti pro verzi Visual Studio 2017 došlo ke spuštění a řešení zatížení výkonu. Při jako Visual Studio team platformy, jsme jste pracovali obecně zlepšení výkonu zatížení spuštění a řešení, naše telemetrie navrhuje nainstalovaná rozšíření může také mít značný vliv na tyto scénáře.

Pomoc uživatelům s porozumění tomuto vlivu, jsme přidali nové funkce v sadě Visual Studio, který upozorní uživatele na pomalé rozšíření. Když Visual Studio zjistí nové rozšíření, která je zpomalení řešení načtení nebo spuštění, uživatelům se zobrazí oznámení v prostředí IDE odkazem na dialogové okno Nový "Správa Visual Studio výkon". Toto dialogové okno je přístupný také vždy nabídku Nápověda k nalezení dříve zjištěné rozšíření.

![Spravovat performace Visual Studio](media/manage-performance.png)

Cílem tohoto dokumentu je pomoci vývojářům při rozšíření prostřednictvím popisu výpočtu rozšíření dopad a jak lze analyzovat lokálně otestovat, pokud rozšíření se může zobrazit jako rozšíření, které mají vliv výkon.

> [!NOTE]
> Tento dokument se zaměřuje na dopad rozšíření na spuštění a řešení zatížení. Rozšíření také ovlivnit výkon sady Visual Studio, když způsobí Uživatelském rozhraní přestat reagovat. Další informace v tomto tématu najdete v tématu [postupy: diagnostikování uživatelské rozhraní se zpozdí způsobené rozšíření](how-to-diagnose-ui-delays-caused-by-extensions.md).

## <a name="how-extensions-can-impact-startup"></a>Jak rozšíření může mít vliv na spuštění

Mezi nejběžnější způsoby pro rozšíření, která mají vliv na výkon při spuštění je rozhodnete automaticky zatížení v některém z uživatelského rozhraní kontexty známé spuštění například NoSolutionExists nebo ShellInitialized. Tyto uživatelské rozhraní kontexty získat aktivuje při spuštění a všechny balíčky, které zahrnují atribut "ProvideAutoLoad" v jejich definice s těmito kontexty budou načtena a inicializovat v daném čase.

Když jsme měřit dopad rozšíření, především zaměříme na času stráveného tyto přípony, které se rozhodnete automaticky načíst v kontextech výše. Měří časy by zahrnovat ale není omezena na:

* Načítání sestavení rozšíření pro synchronní balíčky
* Čas strávený v konstruktoru třídy balíčku pro synchronní balíčky
* Čas strávený v balíčku inicializovat (nebo setsite –) metoda synchronní balíčků
* Pro asynchronní balíčky spuštění vlákna na pozadí na výše uvedené operace a proto jsou vyloučeny z monitorování
* Čas strávený v jakékoli asynchronní pracovní naplánována na spuštění v hlavní vlákno během inicializace balíčku
* Čas strávený v obslužné rutiny událostí, konkrétně prostředí inicializovat kontext aktivace nebo změna stavu zombie prostředí
* Spuštění z Visual Studio 2017 Update 3, také spustíme monitorování čas strávený v nečinnosti, po volání před inicializací prostředí. Dlouhé operace v nečinnosti obslužné rutiny také způsobit reagovat IDE a přispívat k dosahovaný spuštění uživatelem.

Jsme přidali více funkcí spuštění z Visual Studia 2015, chcete-li pomoc s odstraněním potřebu balíčky, které mají automaticky zatížení, odložte jejich zatížení na podrobnější případy, kdy uživatelé by více určité rozšíření nebo snížit dopad rozšíření při načítání automaticky.

Další informace o těchto funkcích naleznete v následujících dokumentech:

[Pravidla na základě uživatelského rozhraní kontexty](how-to-use-rule-based-ui-context-for-visual-studio-extensions.md): modul bohatší založený na pravidlech vytvořených na základě uživatelského rozhraní kontexty umožňují vytvářet vlastní kontexty na základě typy projektů, typů a možnosti. Tato vlastní kontexty slouží k načtení balíčku během více konkrétní scénáře, jako je přítomnost projekt se konkrétní funkce místo spuštění; nebo můžete nastavit [příkaz viditelnost ke stažení na vlastní kontext](visibilityconstraints-element.md) na základě možnosti projektu nebo jiné dostupné podmínky eliminovat potřebu načíst balíček k registraci obslužná rutina příkazu stav dotazu.

[Podpora asynchronní balíček](how-to-use-asyncpackage-to-load-vspackages-in-the-background.md): nové AsyncPackage základní třídy v sadě Visual Studio 2015 umožňuje sadě Visual Studio balíčky, které mají být načíst na pozadí asynchronně, pokud balíček zatížení požadoval uživatel atribut automaticky zatížení nebo dotaz asynchronní služby . Tato načítání pozadí umožňuje IDE zůstane přizpůsobivý při inicializaci rozšíření na pozadí a kritických scénářů, jako je spuštění a řešení zatížení nebude mít vliv.

[Asynchronní služby](how-to-provide-an-asynchronous-visual-studio-service.md): S podporou asynchronní balíček jsme přidali i podpora pro dotazování services asynchronně a schopnost zaregistrovat asynchronní služby. Je důležité pracujeme na převod základní služby Visual Studio pro podporu asynchronní dotazu, takže většinu práce v dotazu asynchronní dojde v vlákna na pozadí. SComponentModel (Visual Studio MEF hostitel) je jedním z hlavních služby, které teď podporuje asynchronní dotazu umožňující rozšíření, které podporují asynchronní načítání úplně.

## <a name="reducing-impact-of-auto-loaded-extensions"></a>Snižuje dopad automaticky načíst rozšíření

Pokud stále musí být automaticky načíst při spuštění balíčku, je důležité minimalizovat objem práce během inicializace balíček postup pro omezení pravděpodobnosti rozšíření spuštění, které mají vliv.

Některé příklady, které by mohly způsobit balíček inicializace drahé jsou:

### <a name="use-of-synchronous-package-load-instead-of-asynchronous-package-load"></a>Použití synchronní balíček zatížení místo zatížení asynchronní balíčku

Protože synchronní balíčky jsou načteny na hlavní vlákno ve výchozím nastavení, doporučujeme vlastníky rozšíření, které mají automaticky načíst balíčky základní třídy asynchronní balíčku použijte místo toho, jak je uvedeno výše. Změna načíst balíček automaticky pro podporu asynchronní načítání bude také usnadňují vyřešit následující problémy.

### <a name="synchronous-filenetwork-io-requests"></a>Synchronní souboru nebo síťových vstupně-výstupní požadavky

V ideálním případě žádnou synchronní žádostí o vstupně-výstupní soubor nebo sítě je nutno v hlavní vlákno jako jejich dopad bude záviset na stav počítače a pro dlouhou dobu v některých případech můžete zablokovat.

Pomocí balíčku asynchronní načítání a asynchronní vstupně-výstupní operace rozhraní API by měl zajistěte, aby balíček inicializace neblokuje hlavní vlákno v takových případech a uživatelé mohou i nadále pracovat s Visual Studio při vstupně-výstupní požadavky dojít v pozadí.

### <a name="early-initialization-of-services-components"></a>Časná inicializace služby součásti

Jednou z běžných vzorech v balíčku inicializace je k chybě při inicializaci služby používané nebo poskytované tento balíček v metodě konstruktoru nebo inicializovat balíčku. Když to zajistí, že služby jsou připravené k použití, můžete také přidat zbytečné náklady na balíček načítání, pokud nejsou okamžitě použity tyto služby. Místo toho je třeba inicializovat tyto služby na vyžádání, chcete-li minimalizovat objem práce v balíčku inicializace.

Pro zadaný balíček služeb global services můžete použít AddService metody, které přijímá funkce líné inicializovat službu jenom v případě, že je požadovaná součást. Pro služby používané v rámci balíčku, můžete využít Lazy<T> nebo AsyncLazy<T> zajistit služby inicializovat ani zjišťovat při prvním použití.

## <a name="measuring-impact-of-auto-loaded-extensions-using-activity-log"></a>Měření dopad automaticky načíst rozšíření pomocí protokolu aktivit

Od verze Visual Studio 2017 Update 3, protokol aktivit v sadě Visual Studio ale bude teď obsahovat na záznamy pro balíčky vlivu na výkon při spuštění a řešení zatížení. Chcete-li zobrazit tyto měření, budete muset spuštění sady Visual Studio s přepínačem/log a otevřete soubor ActivityLog.xml.

V protokolu aktivit, budou v části "Správa Visual Studio výkonu" zdroj položky a bude vypadat podobně jako následující:

```Component: 3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c, Inclusive Cost: 2008.9381, Exclusive Cost: 2008.9381, Top Level Inclusive Cost: 2008.9381```

To znamená, že balíček s identifikátorem GUID "3cd7f5bf-6662-4ff0-ade8-97b5ff12f39c" stráví 2008 ms v spuštění sady Visual Studio. Všimněte si, že Visual Studio zvažuje náklady na nejvyšší úrovni jako primární číslo při výpočet dopad balíčku, která by byla savigs uživatel uvidí, když se rozšíření pro tento balíček zakázat.

## <a name="measuring-impact-of-auto-loaded-extensions-using-perfview"></a>Měření dopad automaticky načíst rozšíření pomocí nástroje PerfView

Během analýzy kódu vám může pomoci identifikovat cesty kódu, které mohou být zpomaleny inicializace balíček, můžete také používat trasování pomocí aplikací, jako nástroje PerfView pochopit dopad balíček zatížení v sadě Visual Studio spuštění.

Nástroje PerfView je nástroj široké trasování systému, který vám pomůže porozumět aktivní cesty v aplikaci buď z důvodu využití procesoru nebo blokování systémová volání. Níže je zběžný příklad na Analýza Ukázka rozšíření pomocí nástroje PerfView k dispozici na [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=28567).

**Příklad kódu:**

Tento příklad vychází z ukázky kódu níže, který je určený k zobrazit případ některé běžné příčiny zpoždění:

```csharp
protected override void Initialize()
{
    // Initialize a class from another assembly as an example
    MakeVsSlowServiceImpl service = new MakeVsSlowServiceImpl();

    // Costly work in main thread involving file IO
    string systemPath = Environment.GetFolderPath(Environment.SpecialFolder.Windows);
    foreach (string file in Directory.GetFiles(systemPath))
    {
        DateTime creationDate = File.GetCreationTime(file);
    }

    // Costly work after shell is initialized. This callback executes on main thread
    KnownUIContexts.ShellInitializedContext.WhenActivated(() =>
    {
        DoMoreWork();
    });

    // Start async work on background thread
    DoAsyncWork().Forget();
}

private async Task DoAsyncWork()
{
    // Switch to background thread to do expensive work
    await TaskScheduler.Default;
    System.Threading.Thread.Sleep(500);
}

private void DoMoreWork()
{
    // Costly work
    System.Threading.Thread.Sleep(500);
    // Blocking call to an asynchronous work.
    ThreadHelper.JoinableTaskFactory.Run(async () => { await DoAsyncWork(); });
}
```

**Záznam trasování pomocí nástroje PerfView:**

Jakmile je nastavit prostředí sady Visual Studio s rozšíření nainstalovat, můžete zaznamenat trasování spuštění otevřením nástroje PerfView a otevírání shromažďování dialogu nabídce "Shromažďovat".

![shromažďování nabídky Nástroje perfview](media/perfview-collect-menu.png)

Výchozí možnosti poskytne zásobníky volání pro spotřeby procesoru, ale vzhledem k tomu, že jsme také blokování čas zajímají, také měli byste povolit zásobníky "Vláken čas". Po nastavení připraveni můžete kliknutím na "spustit"kolekce a spuštění sady Visual Studio, jakmile začne záznam.

Před zastavením shromažďování chcete zkontrolujte, zda je plně inicializovat Visual Studio, hlavní okno je zcela viditelná a pokud rozšíření všech částí uživatelského rozhraní, které se automaticky zobrazí, jsou také viditelné. Jakmile sady Visual Studio je zcela načten a toto rozšíření je inicializován, můžete zastavit záznam k analýze trasování.

**Analýza trasování pomocí nástroje PerfView:**

Po dokončení nahrávání nástroje PerfView automaticky otevřete trasování a možnosti.

Pro účely tohoto příkladu jsme zajímají hlavně "Zásobníky vlákna čas" zobrazení, které můžete najít v části "Skupina rozšířené". Toto zobrazení zobrazí celkový čas strávený metodou včetně čas procesoru a blokovaný čas, jako je třeba v/v disku nebo na obslužné rutiny čekání na vlákno.

 ![zásobníky vlákna čas](media/perfview-thread-time-stacks.png)

 Při otevírání "Zásobníky vlákna čas" zobrazení, měli byste vybrat "devenv" proces zahájíte analýzu.

Nástroje PerfView obsahuje podrobné pokyny o tom, jak číst vlákno zásobníky čas v části vlastní nabídce Nápověda pro více podrobné analýzy. Pro účely tohoto příkladu jsme chcete filtrovat dále v tomto zobrazení pouze zahrnutím zásobníky s vláknem naše balíčky modulu spuštění a název.

1. "GroupPats" nastaven na prázdný text k odebrání všech seskupení přidán ve výchozím nastavení.
2. Sada "IncPats" zahrnout část název sestavení a spuštění vlákna kromě existující proces filtru. V takovém případě je nutné "devenv; Spuštění podprocesu. MakeVsSlowExtension".

Zobrazení se nyní zobrazí pouze náklady spojené s sestavení související se rozšíření. V tomto zobrazení kdykoli uvedené v části "Inc" (včetně náklady) sloupec spuštění vlákna souvisí s našeho filtrovaných rozšíření a ovlivnit spuštění.

V příkladu výše některé zajímavé volání by být zásobníky:

1. Použití třídy System.IO vstupně-výstupní operace: včetně náklady na těchto snímků nemusí být velmi náročná v trasování, jsou potenciální příčinou problém vzhledem k tomu, že soubor rychlost vstupně-výstupní operace se bude lišit počítače z počítače.

  ![rámce vstupně-výstupní operace systému](media/perfview-system-io-frames.png)

2. Blokování volání čekání na další asynchronní pracovní: V tomto případě by včetně čas představují čas, hlavní vlákno je blokované na dokončení asynchronního práce.

  ![blokování volání rámce](media/perfview-blocking-call-frames.png)

Bude jeden z ostatních zobrazení v trasování, které budou užitečné k určení vlivu "Zatížení zásobníky bitové kopie". Můžete použít stejné filtry jako použít pro zobrazení "Zásobníky vlákna čas" a zjistěte, ve všech sestaveních načíst z důvodu kód provedený váš automaticky načíst balíček.

Je důležité, chcete-li minimalizovat počet načtených sestavení uvnitř inicializační rutina balíček jako každé další sestavení bude zahrnovat vstupy/výstupy navíc disků, které může zpomalit spuštění podstatně na počítačích pomalejší.

## <a name="summary"></a>Souhrn

Spuštění sady Visual Studio, musí být jeden z oblasti, které jsme průběžně získání zpětné vazby. Naším cílem, jak je uvedeno výše je pro všechny uživatele tak, aby měl konzistentní spuštění prostředí bez ohledu na to, komponenty a rozšíření, která mají být nainstalovány a rádi bychom se pracovat s vlastníky rozšíření je Pomozte nám dosažení tohoto cíle pomohou. Výše uvedených pokynů by měl být užitečné vysvětlující Princip fungování rozšíření dopad na spuštění a buď nebudete muset automaticky zatížení nebo zatížení asynchronně k minimalizaci vlivu na produktivitu uživatelů.
