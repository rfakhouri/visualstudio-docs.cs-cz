---
title: Začínáme s laděním v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 12/14/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 085ea00f95124eb6ae2ed7ccc96eed692be0d649
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-debugging-in-visual-studio"></a>Začínáme s laděním v sadě Visual Studio
Visual Studio poskytuje výkonnou sadu integrované sestavení projektu a nástroje pro ladění. V tomto tématu zjistěte, jak začít používat sadu nejzákladnější ladění funkcí uživatelského rozhraní.  

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>Vlastní kód nefunguje. Pomozte mi, Visual Studio  
 Takže jste započítáno out editoru a vytvoříte nějaký kód. Nyní budete chtít spustit ladění tento kód. V sadě Visual Studio, stejně jako u většiny integrovaného vývojového prostředí, existují dvě fáze k ladění: vytváření kódu zachytit a vyřešit chyby projektu a kompilátoru; a spuštění tohoto kódu v prostředí zachytit a řešení chyb při běhu a dynamické.  

### <a name="build-your-code"></a>Sestavení kódu  
 Existují dva základní typy konfigurace sestavení: **ladění** a **verze**. První konfigurace vytvoří pomalejší, větší spustitelný soubor, který umožňuje bohatší interaktivní ladění možnosti spuštění, ale nikdy dodání. Druhý sestavení rychlejší, více optimalizované spustitelný soubor, který je vhodný pro odeslání (alespoň z perspektivy kompilátor). Výchozí konfigurace sestavení **ladění**.

Nejjednodušší způsob, jak sestavit projekt je ke stisknutí **F7**, ale můžete také spustit sestavení tak, že vyberete **sestavení > Sestavit řešení** z hlavní nabídky.  

 ![Visual Studio sestavení projektu nabídky Výběr](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 Můžete sledovat v procesu sestavení **výstup** stavové okno, v dolní části rozhraní Visual Studia. Operace sestavení, upozornění a chyb se zobrazí tady. Pokud máte chyby (nebo pokud máte upozornění výše nakonfigurované úrovni), vaše sestavení se nezdaří. Kliknutím na s chybami a upozorněními přejít na řádek, kde k nim došlo. Znovu sestavte projekt stisknutím buď **F7** znovu (a znovu zkompiluje pouze soubory s chybami) nebo **Ctrl + Alt + F7** (pro vyčištění a úplné opětovné sestavení).  

 Existují dvě sestavení s kartami windows v okně výsledky níže editoru: **výstup** okno, které obsahuje nezpracovaná kompilátoru výstup (včetně chybových zpráv) a **seznam chyb** okno, které poskytuje řazení a filtrování seznamu všechny chyby a upozornění.  

 Po úspěšné, zobrazí se výsledky jako to **výstup** okno.  

 ![Visual Studio úspěšné vytvoření výstupu](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="review-the-error-list"></a>Zkontrolujte seznam chyb  
 Pokud jste udělali žádné úpravy kód, který jste si dříve a úspěšně zkompilovány, pravděpodobně jste chybu. Pokud jste nové kódování, pravděpodobně máte spoustu je. Chyby jsou někdy zřejmé, jako je jednoduchý syntaktickou chybu nebo nesprávný název proměnné a někdy jsou těžko srozumitelné s pouze jako nesrozumitelné kód na vás. Čisticí zobrazit problémy, přejděte k dolnímu okraji sestavení **výstup** a klikněte na **seznam chyb** kartě. Tím přejdete na více uspořádaný náhled chyb a varování pro svůj projekt a vám dává některé další možnosti.  

 ![Výstup sady Visual Studio a seznam chyb](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 Klikněte na řádek chyby ve **seznam chyb** okno a přechod na řádek v dojde k chybě. (Nebo zapnout čísla řádků kliknutím v **Snadné spuštění** panel v pravém horním, zadáním "čísla řádků" do ní a klávesy **Enter**. Toto je nejrychlejší způsob, jak získat k **možnosti** položka okno, kde můžete zapnout čísla řádků. Naučte se používat **Snadné spuštění** panel a ušetřit spoustu kliknutí uživatelského rozhraní!)  

 ![Visual Studio editor s čísla řádků](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Visual Studio řádku čísla možnost](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 Použití **kombinaci kláves Ctrl + G** k rychlému přechodu do číslo řádku, na kterém došlo k chybě.  

 Chyba je identifikována red "klikatá" podtržítka. Pozastavte ukazatel myši nad jeho další podrobnosti. Proveďte opravu a jeho zmizí, i když může znamenat nové chyby s oprava. (To se nazývá "regrese".)  

 ![Visual Studio chyba hover](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 Provede v seznamu chyb a vyřešte všechny chyby v kódu.  

 ![Visual Studio ladění chyb okno](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="review-errors-in-detail"></a>Zkontrolujte chyby v podrobností  
 Mnoho chyb má smysl žádné vám obsahuje jiné spojení, jako jsou v podmínkách kompilátoru. V takových případech budete potřebovat další informace. Z **seznam chyb** okno, můžete provést automatické vyhledávání Bing Další informace o chyba (nebo upozornění) podle pravým tlačítkem myši na řádku odpovídající položky a výběrem **zobrazit nápovědu k chybě** z kontextové nabídky.  

 ![Visual Studio seznam chyb Bing vyhledávání](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 Na kartě v sadě Visual Studio spustí který je hostitelem výsledky Bing vyhledejte kód chyby a text. Výsledky jsou z mnoha různých zdrojů v síti Internet, a ne všechny může být užitečné.  

 Případně můžete kliknutím na hodnotu s hypertextovým odkazem chyba kódu v **kód** sloupec **seznam chyb**. Tím se spustí vyhledávání Bingu pro kód chyby.  

### <a name="use-light-bulbs-to-fix-or-refactor-code"></a>Pomocí žárovek opravíte nebo Refaktorovat kódu  
 Žárovek jsou nová funkce pro Visual Studio, která vám umožní Refaktorovat vloženého kódu. Jsou snadný způsob, jak opravit běžné upozornění rychle a efektivně. Chcete-li přistupovat k nim, klikněte pravým tlačítkem na upozornění vlnovku (nebo stiskněte klávesu **Ctrl +**. Při ukazatele myši vlnovka) a potom vyberte **rychlé akce**.  

 ![Žárovky rychlé možnosti aplikace Visual Studio](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 Zobrazí se seznam možných opravy nebo refactors, které můžete provést u tohoto řádku kódu.  

 ![Visual Studio žárovky preview](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 Žárovek lze použít bez ohledu na analyzátorů kódu určit, že je možnost pro opravu, refactor, nebo vylepšení vašeho kódu. Klikněte na každý řádek kódu, pravým tlačítkem a otevřete kontextu nabídku a vyberte **rychlé akce** (nebo znovu, pokud dáváte přednost efektivitu, stiskněte **Ctrl +**.). Pokud jsou k dispozici refaktoring nebo zlepšování možností, budou zobrazena; v opačném zpráva `No quick options available here` se zobrazí v lůžkem levém dolním rohu okna IDE.  

 ![Visual Studio žárovky light – žádná možnost text](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 V prostředí, můžete rychle použít klávesy se šipkami a **Ctrl +**. pro kontrolu rychlé možnosti refaktoring příležitostí a vyčistit kódu!  

 Další informace o žárovek číst [rychlé akce pomocí žárovek](../ide/perform-quick-actions-with-light-bulbs.md).  

### <a name="debug-your-running-code"></a>Ladění spuštěním kódu  
 Teď, když jste úspěšně sestaven kódu a provést trochu vyčistit, spusťte stisknutím **F5** nebo výběr **ladění > Spustit ladění**. Tím spustíte aplikaci v prostředí ladění, můžete sledovat své chování podrobně. Visual Studio IDE změní, když aplikace běží: **výstup** okno nahrazeno dva nové (v konfiguraci okna výchozí), **automobily/místní hodnoty nebo sledování** – záložkami okno a **Volání nastavení výstupní zásobník/zarážky nebo výjimka** okno s kartami. Tyto windows mají několik karet, které vám umožní prohlédnout a vyhodnocení proměnné vaší aplikace, vláken, zpětná volání a různé další chování při jeho spuštění.  

 ![Visual Studio automobily a volání zásobníku Windows](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 Aplikace můžete zastavit stisknutím **Shift + F5** nebo kliknutím **Zastavit** tlačítko. Nebo můžete jednoduše zavřít hlavní okno aplikace (nebo dialogové okno příkazového řádku).  

 V případě kódu spustil perfektně a přesně podle očekávání, Blahopřejeme! Ale pokud přestala, nebo došlo k chybě nebo vám Dal některé neobvyklé výsledky, budete potřebovat najít zdroj těchto problémů a opravte chyby.  

### <a name="set-simple-breakpoints"></a>Nastavit jednoduché zarážky  
 Zarážky jsou nejvíce základní a základní funkci spolehlivé ladění. Zarážku Určuje, kde by měl Visual Studio pozastavit spuštěním kódu, můžete si prohlédněte hodnoty proměnných nebo chování paměti, nebo zda získávání větev kódu běží. NENÍ nutné znovu sestavit projekt po nastavení a odebírání zarážky.  

 Zarážku kliknutím v úplně okraj řádku místo rozdělení dojít nebo stiskněte klávesu **F9** nastavit zarážky na aktuálním řádku kódu. Při spuštění kódu se pozastaví (nebo *zalomení*) předtím, než se spustí pokyny pro tento řádek kódu.  

 ![Visual Studio breakpoint](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")   

 Mezi běžná použití pro zarážky patří:  

1.  Chcete-li zúžit zdroj havárie nebo zablokuje, bodový je v rámci a kolem kód volání metody, které se domníváte, že je příčinou selhání. Jako při spuštění kódu v ladicím programu odebrat a poté resetujte zarážky blíže společně vyhledejte problematické řádek kódu.  Najdete v další části se dozvíte, jak spustit kód v ladicím programu.

2.  Když zavedete nový kód, zarážku na začátku ji a spusťte kód a ujistěte se, že se chová podle očekávání.

3.  Pokud jste implementovali složité chování, nastavte zarážky pro algoritmické kód, tak při rozdělení si můžete prohlédnout hodnoty proměnných a data.  

4.  Pokud jsou psaní kódu jazyka C nebo C++, použijte zarážky pro zastavení kód, takže si můžete prohlédnout hodnoty adres (podívejte se na hodnotu NULL) a počty odkazů při ladění chyby související s pamětí.  

 Další informace o použití zarážek, najdete v tématu [použití zarážek](../debugger/using-breakpoints.md).  

### <a name="inspect-your-code-at-run-time"></a>Kontrola kódu v době běhu  
 Při spuštění kódu dotkne boru přerušení a pozastaví, nebyl ještě provést řádek kódu označena žlutě (aktuální příkaz). V tomto okamžiku můžete provést aktuální příkaz a zkontrolujte změněné hodnoty. Můžete použít několik *krok* příkazů pro spuštění kódu v ladicím programu. Pokud je označen jako kód volání metody, můžete do ní krok stisknutím **F11**. Můžete také *krok přes* řádek kódu stisknutím **F10**. Další příkazy a podrobnosti o tom, jak procházet kód, přečtěte si [přejděte kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).

 ![Visual Studio spustit&#45;čas hodnota kontroly](../ide/media/vs_ide_gs_debug_hit_breakpoint.PNG "vs_ide_gs_debug_inspect_value")

 V předchozí ilustraci postoupíte ladicí program jeden příkaz stisknutím buď **F10** nebo **F11** (vzhledem k tomu, že není zde žádná volání metody, jak příkazy mají stejný výsledek).

 Při ladicího programu je pozastavena, můžou kontrolovat proměnných a k určení, co se děje zásobníky volání. Hodnoty jsou v oblastech, které byste měli vidět? Jsou volání určené ve správném pořadí?  

 ![Visual Studio spustit&#45;čas hodnota kontroly](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 Podržte ukazatel nad proměnné zobrazíte hodnoty a odkazy, které aktuálně obsahuje. Pokud se zobrazí hodnota, kterou by neměl být, pravděpodobně chyby v předchozích nebo volání řádků kódu.  Podrobnější informace [Další](../debugger/getting-started-with-the-debugger.md) o používání ladicího programu.

 Kromě toho Visual Studio zobrazí **diagnostické nástroje** okno, kde můžete sledovat využití procesoru a paměti vaší aplikace v čase. Později ve vývoji vaší aplikace můžete tyto nástroje Pokud chcete vyhledat neočekávané velkou využití nebo paměť přidělení procesoru. Použít ve spojení s **sledovat** okno a zarážky pro příčinu neočekávané velkou využití nebo nevydané prostředky.  Další informace najdete v tématu [profilace prohlídka funkce](../profiling/profiling-feature-tour.md).

### <a name="run-unit-tests"></a>Spouštění testování částí  
 Testování částí se vaše první linií obrany před kódu chyby proto, že pokud jsou správně provedené, testují jedné "jednotka" kódu, obvykle jednu funkci a jsou obvykle mnohem snazší ladit než ladění vašeho úplné programu. Visual Studio nainstaluje rozhraní testování částí Microsoft pro spravovaná a nativní kód. Použijte testování framework částí vytvářet testy částí, spustit je a ohlásí výsledky tyto testy. Testování částí spusťte při provádění změn pro testování, aby váš kód stále funguje správně. Pokud používáte Visual Studio Enterprise edition, můžete spustit testy automaticky po každé sestavení.  

 Chcete-li začít, přečtěte si [generování testů částí kódu s IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).  

 Další informace o testování částí v sadě Visual Studio a jak se vám pomůžou vytvořit lepší kvality kódu, přečtěte si [jednotkové testování Základy](../test/unit-test-basics.md).  

### <a name="perform-static-code-analysis"></a>Provedení analýzy statické kódu  
 "Analýza kódu statických" je zvláštní způsob oznámením "automaticky zkontrolujte vlastní kód pro běžné problémy, které může vést k běhové chyby nebo problémy ve správě kódu". Získání v která podporují jejího spuštění, když jste odstranili zřejmé chyby brání sestavení a nějakou dobu adres, které může vytvořit upozornění. Můžete budete uložit sami některé hlavu dolů na cestách, jakož i další pár techniky styl kódu.  

 Stiskněte klávesu **Alt + F11** (nebo vyberte **analyzovat > spustit analýza kódu v řešení** z hlavní nabídky) spusťte analýza statické kódu. Pokud máte velké množství kódu, může to chvíli trvat.  

 ![Položky nabídky Visual Studio Code Analysis](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 Všechny nové nebo aktualizované upozornění se zobrazí v **seznam chyb** karta v dolní části rozhraní IDE. Klikněte na upozornění přejít k nim.  

 ![Seznam chyb Visual Studio s upozorněními](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 Upozornění budou označeny s jasně vlnovku žlutý zelená místo red jeden. Pozastavte ukazatel myši nad je podrobné informace a klikněte pravým tlačítkem na jejich získat z kontextové nabídky, které vám pomohou v opravy nebo refaktoringu možnosti.  

 ![Visual Studio Code Analysis upozornění hover](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

## <a name="see-also"></a>Viz také  
 [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)  
 [Další informace o používání ladicího programu](../debugger/getting-started-with-the-debugger.md)
