---
title: "Začínáme s laděním v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: "5"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 82bce617eec0f5038499a2eed370efa33d817e20
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-debugging-in-visual-studio"></a>Začínáme s laděním v sadě Visual Studio
Visual Studio poskytuje výkonnou sadu integrované sestavení projektu a nástroje pro ladění. V tomto tématu zjistěte, jak začít používat sadu nejzákladnější ladění funkcí uživatelského rozhraní.  

 Poznámka: Odkazy na témata příslušnou platformu nebo funkce a dalších pokročilých funkcí se v dolní části této stránky.  

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>Vlastní kód nefunguje. Pomozte mi, Visual Studio  
 Takže jste započítáno out editoru a vytvoříte nějaký kód. Nyní budete chtít spustit ladění tento kód. V sadě Visual Studio, stejně jako u většiny integrovaného vývojového prostředí, existují dvě fáze k ladění: vytváření kódu zachytit a vyřešit chyby projektu a kompilátoru; a spuštění tohoto kódu v prostředí zachytit a řešení chyb při běhu a dynamické.  

### <a name="configuring-a-build"></a>Konfigurace sestavení  
 Existují dva základní typy konfigurace sestavení: **ladění** a **verze**. První konfigurace vytvoří pomalejší, větší spustitelný soubor, který umožňuje bohatší interaktivní ladění možnosti spuštění, ale nikdy dodání. Druhý sestavení rychlejší, více optimalizované spustitelný soubor, který je vhodný pro odeslání (alespoň z perspektivy kompilátor).  

 Výchozí konfigurace sestavení **ladění**.  

 ![Visual Studio ladění sestavení tlačítko](../ide/media/vs_ide_gs_debug_build_type1.PNG "Vs_ide_gs_debug_build_type1")  

 Můžete také zadat konkrétní sestavení platformu pro cíl, například **x86** (procesory Intel 32-bit), **x64** (procesory Intel 64-bit), a **ARM** (procesory ARM, podporuje jenom pro některé aplikace typy). Výchozí hodnota je **x86** pro projekty spravovaná a nativní. Jak ho změnit, klikněte na rozevírací platformy sestavení a vyberte jiné platformy nebo **nástroje Configuration Manager...**  

 ![Okno Visual Studio konfigurační soubor správce](../ide/media/vs_ide_gs_debug_build_cf_mgr.PNG "Vs_ide_gs_debug_build_cf_mgr")  

 Můžete zadat cílové sestavení konfigurace pomocí **nástroje Configuration Manager**. Spusťte ji, klikněte na tlačítko **konfigurace** nebo **procesoru** rozevíracího seznamu a vyberte **nový...**  k vytvoření nového sestavení nebo platformu.  

 ![Visual Studio Configuration Manager okno](../ide/media/vs_ide_gs_debug_build_cf_mgr_2.PNG "Vs_ide_gs_debug_build_cf_mgr_2")  

 Začínáte, použijte **ladění** a **x86** jako konfiguraci sestavení a platformy, v uvedeném pořadí. Po dokončení kódování a ladění, změňte konfiguraci, aby **verze** a konkrétní platformu. (Starší verze sady Visual Studio poskytuje **AnyCPU** výchozí platforma pro projekty pro kód .net.)  

 Poznámka: Při sestavování projektu hodnoty konfigurace a platformy se taky používají k určení, jaké cesta k adresáři projektu je vytvořena pro uložení spustitelný soubor. Obvykle je to  **\<cesta k projektu >\\< název projektu >\\< konfigurace\>\\< platforma\>**. Například projektu s konfigurací `Debug` a platforma z `x86` by naleznete pod `Projects\MyProjectNameHere\MyProjectNameHere\bin\Debug\x86`. To může být užitečné, pokud máte vlastní nástroje nebo skripty, které Správa těchto předdefinovaných spustitelných souborů.  

### <a name="building-your-code"></a>Vytváření kódu  
 S buildu nakonfigurován je čas k ve skutečnosti sestavení projektu. Nejjednodušší způsob, jak provést ke stisknutí F7, ale můžete také spustit sestavení tak, že vyberete **sestavení -> Sestavit řešení** z hlavní nabídky.  

 ![Visual Studio sestavení projektu nabídky Výběr](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 Můžete sledovat v procesu sestavení **výstup** stavové okno, v dolní části rozhraní Visual Studia. Operace sestavení, upozornění a chyb se zobrazí tady. Pokud máte chyby (nebo pokud máte upozornění výše nakonfigurované úrovni), vaše sestavení se nezdaří. Kliknutím na s chybami a upozorněními přejít na řádek, kde k nim došlo. Znovu sestavte projekt stisknutím buď **F7** znovu (a znovu zkompiluje pouze soubory s chybami) nebo **Ctrl + Alt + F7** (pro vyčištění a úplné opětovné sestavení).  

 Existují dvě sestavení s kartami windows v okně výsledky níže editoru: **výstup** okno, které obsahuje nezpracovaná kompilátoru výstup (včetně chybových zpráv) a **seznam chyb** okno, které poskytuje řazení a filtrování seznamu všechny chyby a upozornění.  

 Po úspěšné, zobrazí se výsledky jako to **výstup** okno.  

 ![Visual Studio úspěšné vytvoření výstupu](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="reviewing-the-error-list"></a>Kontrola seznamu chyb  
 Pokud jste udělali žádné úpravy kód, který jste si dříve a úspěšně zkompilovány, pravděpodobně jste chybu. Pokud jste nové kódování, pravděpodobně máte spoustu je. Chyby jsou někdy zřejmé, například jednoduché syntaktickou chybu nebo nesprávný název proměnné a někdy jsou těžko srozumitelné s pouze jako nesrozumitelné kód na vás. Čisticí zobrazit problémy, přejděte k dolnímu okraji sestavení **výstup** a klikněte na **seznam chyb** kartě. Tím přejdete na více uspořádaný náhled chyb a varování pro svůj projekt a vám dává některé další možnosti.  

 ![Výstup sady Visual Studio a seznam chyb](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 Klikněte na řádek chyby ve **seznam chyb** okno a přechod na řádek v dojde k chybě. (Nebo zapnout čísla řádků kliknutím v **Snadné spuštění** panel v pravém horním, zadejte "čísla řádků" do ní a stisknutím klávesy Enter. Toto je nejrychlejší způsob, jak získat k **možnosti** položka okno, kde můžete zapnout čísla řádků. Naučte se používat **Snadné spuštění** panel a ušetřit spoustu kliknutí uživatelského rozhraní!)  

 ![Visual Studio editor s čísla řádků](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Visual Studio řádku čísla možnost](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 Pomocí kombinace kláves Ctrl + G k rychlému přechodu do číslo řádku, na kterém došlo k chybě.  

 Chyba je identifikována red "klikatá" podtržítka. Pozastavte ukazatel myši nad jeho další podrobnosti. Proveďte opravu a jeho zmizí, i když může znamenat nové chyby s oprava. (To se nazývá "regrese".)  

 ![Visual Studio chyba hover](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 Provede v seznamu chyb a vyřešte všechny chyby v kódu.  

 ![Visual Studio ladění chyb okno](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="reviewing-errors-in-detail"></a>Kontrola chyb podrobně  
 Mnoho chyb má smysl žádné vám obsahuje jiné spojení, jako jsou v podmínkách kompilátoru. V takových případech budete potřebovat další informace. Z **seznam chyb** okno, můžete provést automatické vyhledávání Bing Další informace o chyba (nebo upozornění) podle pravým tlačítkem myši na řádku odpovídající položky a výběrem **zobrazit nápovědu k chybě** z kontextové nabídky.  

 ![Visual Studio seznam chyb Bing vyhledávání](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 Na kartě v sadě Visual Studio spustí který je hostitelem výsledky Bing vyhledejte kód chyby a text. Výsledky jsou z mnoha různých zdrojů v síti Internet, a ne všechny může být užitečné.  

 Případně můžete kliknutím na hodnotu s hypertextovým odkazem chyba kódu v **kód** sloupec **seznam chyb**. Tím se spustí vyhledávání Bingu pro kód chyby.  

### <a name="performing-static-code-analysis"></a>Provádění Statická analýza kódu  
 "Analýza kódu statických" je zvláštní způsob oznámením "automaticky zkontrolujte vlastní kód pro běžné problémy, které může vést k běhové chyby nebo problémy ve správě kódu". Získání v která podporují jejího spuštění, když jste odstranili zřejmé chyby brání sestavení a nějakou dobu adres, které může vytvořit upozornění. Můžete budete uložit sami některé hlavu dolů na cestách, jakož i další pár techniky styl kódu.  

 Stisknutím klávesy Alt + F11 (nebo vyberte **analyzovat -> spustit analýza kódu v řešení** z hlavní nabídky) spusťte analýza statické kódu. Pokud máte velké množství kódu, může to chvíli trvat.  

 ![Položky nabídky Visual Studio Code Analysis](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 Všechny nové nebo aktualizované upozornění se zobrazí v **seznam chyb** karta v dolní části rozhraní IDE. Klikněte na upozornění přejít k nim.  

 ![Seznam chyb Visual Studio s upozorněními](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 Upozornění budou označeny s jasně vlnovku žlutý zelená místo red jeden. Pozastavte ukazatel myši nad je podrobné informace a klikněte pravým tlačítkem na jejich získat z kontextové nabídky, které vám pomohou v opravy nebo refaktoringu možnosti.  

 ![Visual Studio Code Analysis upozornění hover](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

### <a name="using-light-bulbs-to-fix-or-refactor-code"></a>Pro opravu nebo Refaktorovat kódu pomocí žárovek  
 Žárovek jsou nová funkce pro Visual Studio, která vám umožní Refaktorovat vloženého kódu. Jsou snadný způsob, jak opravit běžné upozornění rychle a efektivně. Chcete-li přistupovat k nim, klikněte pravým tlačítkem na upozornění vlnovku (nebo stiskněte klávesy Ctrl +. Při ukazatele myši vlnovka) a potom vyberte **rychlé akce**.  

 ![Rychlé možnosti aplikace Visual Studio žárovky](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 Zobrazí se seznam možných opravy nebo refactors, které můžete provést u tohoto řádku kódu.  

 ![Visual Studio žárovky preview](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 Žárovek lze použít bez ohledu na analyzátorů kódu určit, že je možnost pro opravu, refactor, nebo vylepšení vašeho kódu. Klikněte na každý řádek kódu, pravým tlačítkem a otevřete kontextu nabídku a vyberte **rychlé možnosti** (nebo, znovu, pokud dáváte přednost efektivitu, stiskněte Ctrl +).. Pokud je oblast refaktoring nebo zlepšování možnosti, které jsou k dispozici, zobrazí se; v opačném zpráva `No quick options available here` se zobrazí v lůžkem levém dolním rohu okna IDE.  

 ![Visual Studio žárovky žádná možnost text](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 V prostředí můžete rychle použít klávesy se šipkami a Ctrl +. pro kontrolu rychlé možnost refaktoring příležitostí a vyčistit kódu!  

 Další informace o žárovek číst [rychlé akce pomocí žárovek](../ide/perform-quick-actions-with-light-bulbs.md).  

### <a name="debugging-your-running-code"></a>Ladění kódu spuštěná  
 Teď, když jste úspěšně sestaven kódu a provést trochu vyčistit, spusťte stisknutím klávesy F5 nebo výběrem **-ladění > Spustit ladění**. Tím spustíte aplikaci v prostředí ladění, můžete sledovat své chování podrobně. Visual Studio IDE změní, když aplikace běží: **výstup** okno nahrazeno dva nové (v konfiguraci okna výchozí), **automobily/místní hodnoty nebo moduly nebo sledování** – záložkami okno a  **Volat zásobník/zarážky nebo výjimka nastavení výstupní** okno s kartami. Tyto windows mají několik karet, které vám umožní prohlédnout a vyhodnocení proměnné vaší aplikace, vláken, zpětná volání a různé další chování při jeho spuštění.  

 ![Visual Studio automobily a volání zásobníku Windows](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 Zkuste různých akcí s vaší aplikací a sledovat změny. Pokud se objeví něco nestandardního, pozastavit aplikaci stisknutím kombinace kláves Ctrl + Alt + Break (nebo klikněte na **pozastavit** tlačítko).  

 ![Visual Studio přerušení všech tlačítko](../ide/media/vs_ide_gs_debug_break_all_button.png "vs_ide_gs_debug_break_all_button")  

 Stiskněte klávesu F5, chcete-li pokračovat, spuštění aplikace (nebo klikněte na tlačítko **pokračovat** tlačítko).  

 ![Visual Studio ladění pokračovat tlačítko](../ide/media/vs_ide_gs_debug_continue_button.png "Vs_ide_gs_debug_continue_button")  

 Aplikace můžete zastavit stisknutím kláves Shift + F5 nebo kliknutím **Zastavit** tlačítko. Nebo můžete jednoduše zavřít hlavní okno aplikace (nebo dialogové okno příkazového řádku).  

 V případě kódu spustil perfektně a přesně podle očekávání, Blahopřejeme! Změnit konfiguraci sestavení na **verze** a sestavit pro nasazení! (Odborníci v oblasti chtít přejít na bitu na testování částí na konci, přestože.) Ale pokud přestala, nebo došlo k chybě nebo vám Dal některé neobvyklé výsledky, budete potřebovat najít zdroj těchto problémů a opravte chyby.  

### <a name="setting-simple-breakpoints"></a>Nastavení zarážek jednoduché  
 Zarážky jsou nejvíce základní a základní funkci spolehlivé ladění. Zarážku Určuje, kde by měl Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda získávání větev kódu běží. NENÍ nutné znovu sestavit projekt po nastavení a odebírání zarážky.  

 Nastavte zarážky kliknutím v úplně okraj řádku místo rozdělení na proběhnout, nebo vyberte řádek kódu a stiskněte klávesu F9. Při spuštění kódu zastaví předtím, než se spustí pokyny pro tento řádek kódu.  

 ![Visual Studio zarážek](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")  

 Pokud kód dělí, nebyl ještě spustit označený řádek kódu. V tomto okamžiku můžete provést pokyny pro řádek kódu, které jsou označeny zarážce a zkontrolovat změněné hodnoty. Tomu se říká "zanoříte se do" kód. Pokud je označen jako kód volání metody, můžete stisknutím klávesy F11 krok do ní. Vám může také "Krok přes" řádku kódu stisknutím klávesy F10. Další informace o kódu krokování s, najdete v tématu [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).  

 Mezi běžná použití pro zarážky patří:  

1.  Chcete-li zúžit zdroj havárie nebo zablokuje, bodový je v rámci a kolem kód volání metody, které se domníváte, že je příčinou selhání. Krocích kód odebrat a poté resetujte zarážky blíže společně vyhledejte problematické řádek kódu.  

2.  Když zavedete nový kód, zarážku na začátku a krok prostřednictvím kódu a ujistěte se, že se chová podle očekávání.  

3.  Pokud jste implementovali složité chování, nastavte zarážky pro algoritmické kód, tak při rozdělení si můžete prohlédnout hodnoty proměnných a data.  

4.  Pokud jsou psaní kódu jazyka C nebo C++, použijte zarážky pro zastavení kód, takže si můžete prohlédnout hodnoty adres (podívejte se na hodnotu NULL) a počty odkazů při ladění chyby související s pamětí.  

 Další informace o použití zarážek, najdete v tématu [pomocí zarážek](../debugger/using-breakpoints.md)  

### <a name="setting-conditional-breakpoints"></a>Nastavení podmíněné zarážky  
 Pokud máte zarážka v smyčky nebo rekurze, nebo pokud máte spoustu zarážky, které často krok prostřednictvím, použijte podmíněné zarážky zajistit, aby váš kód je pozastaven, pouze v případě, že jsou splněny určité podmínky. Jinak hodnota je budete mít kombinace F11 awful mnoho.  

 Nastavení podmíněné zarážky a pozastavit kódu, pokud je nastaven na určitou hodnotu proměnné nebo předá určitou mez, klepněte do okraje nastavit zarážky a pak vyberte v nabídce přechodu, který se zobrazí "ikonu".  

 ![Nastavení zarážek sady Visual Studio](../ide/media/vs_ide_gs_debug_breakpoint_settings.png "Vs_ide_gs_debug_breakpoint_settings")  

 Zobrazí se dialogové okno, které vypadá takto kde můžete nastavit konkrétní podmínky pro zalomení.  

 ![Visual Studio podmíněného zarážek](../ide/media/vs_ide_gs_debug_breakpoint_conditional.PNG "Vs_ide_gs_debug_breakpoint_conditional")  

 Další podrobnosti o tom, jak deklarovat výrazy použité k vyhodnocení podmíněné zarážky, podívejte se na Channel9 video [zarážek konfigurace prostředí v sadě Visual Studio](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/711).  

### <a name="inspecting-your-code-at-run-time"></a>Probíhá kontrola kódu v době běhu  
 Pokud se spuštění kódu dotkne zarážku a zdržovalo, můžou kontrolovat proměnných a k určení, co se děje zásobníky volání. Hodnoty jsou v oblastech, které byste měli vidět? Jsou volání určené ve správném pořadí?  

 ![Visual Studio spustit & č. 45; hodnota kontroly času](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 Podržte ukazatel nad proměnné zobrazíte hodnoty a odkazy, které aktuálně obsahuje. Pokud se zobrazí hodnota, kterou by neměl být, pravděpodobně chyby v předchozích nebo volání řádků kódu. Zarážky nahoru nebo přidání podmínek do existující zarážky částečná Další.  

 Kromě toho Visual Studio zobrazí okno diagnostické nástroje, kde můžete sledovat vaše aplikace CPU a využití paměti v čase. Použijte je k vyhledání neočekávané velkou využití nebo paměť přidělení procesoru. Použít ve spojení s **sledovat** okno a zarážky pro příčinu neočekávané velkou využití nebo nevydané prostředky.  

 ![Visual Studio diagnostické nástroje okno](../ide/media/vs_ide_gs_debug_diagnostic_tools.PNG "Vs_ide_gs_debug_diagnostic_tools")  

### <a name="running-unit-tests"></a>Spouštění testů jednotek  
 Testy jednotek jsou programy, které vykonává cesty kódu v aplikaci nebo službě. Visual Studio nainstaluje rozhraní testování částí Microsoft pro spravovaná a nativní kód. Použijte testování framework částí vytvářet testy částí, spustit je a ohlásí výsledky tyto testy. Testování částí spusťte při provádění změn pro testování, aby váš kód stále funguje správně. Pokud používáte Visual Studio Enterprise edition, můžete spustit testy automaticky po každé sestavení.  

 Chcete-li začít, přečtěte si [generování testů částí kódu s IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).  

 Další informace o testování částí v sadě Visual Studio a jak se vám pomůžou vytvořit lepší kvality kódu, přečtěte si [testování částí](../test/unit-test-basics.md).  

## <a name="see-also"></a>Viz také  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)
