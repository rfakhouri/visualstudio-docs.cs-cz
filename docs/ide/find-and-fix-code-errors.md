---
title: Opravte chyby programu a zlepšení kódu
description: Tento článek popisuje některé základní způsoby, jak Visual Studio vám pomůže najít a opravit problémy v kódu, včetně chyby sestavení analýzy kódu, ladění, nástroje a testy jednotek.
ms.date: 05/02/2018
ms.topic: conceptual
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0f1f55f0e0ae9882154ed62ccbf323441070472
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57223608"
---
# <a name="make-code-work-in-visual-studio"></a>Kód pracovat v sadě Visual Studio

Visual Studio poskytuje výkonné integrované sady sestavení projektu a nástroje pro ladění. V tomto článku zjistěte, jak vám může pomoci Visual Studio můžete najít problémy ve vašem kódu pomocí výstupu, sestavení analýzy kódu, nástroje pro ladění a testování částí.

Jste naplánujete editoru a vytvořili nějaký kód. Teď budete chtít Ujistěte se, že kód funguje správně. V sadě Visual Studio, existují dvě fáze pro provádění kódu práce stejně jako u většiny prostředí IDE: sestavování kódu zachytit a řešení chyb projektu a kompilátoru a spouštění kódu najít chyby za běhu a dynamické.

## <a name="build-your-code"></a>Sestavení kódu

Existují dva základní druhy konfigurace sestavení: **Ladění** a **vydání**. **Ladění** konfigurace vytvoří pomalejší, větší spustitelný soubor, který umožňuje pohodlnější a pestřejší interaktivní ladění prostředí za běhu. **Ladění** spustitelný soubor by měl být nikdy dodán. **Vydání** konfigurace sestavení rychlejší, optimalizované spustitelný soubor, který je vhodný k odeslání (alespoň z hlediska kompilátor). Výchozí konfigurace sestavení **ladění**.

Nejjednodušší způsob, jak sestavit projekt je stisknout klávesu **F7**, ale můžete také spustit sestavení tak, že vyberete **sestavení** > **sestavit řešení** z hlavní nabídky.

![Výběr nabídky projekt sestavení sady Visual Studio](../ide/media/vs_ide_gs_debug_build_menu_item.png)

Můžete sledovat v procesu sestavení **výstup** okno v dolní části rozhraní Visual Studia. Zde jsou zobrazeny chyby, varování a operace sestavení. Pokud už máte chyby (nebo pokud máte nakonfigurované úroveň upozornění), vaše sestavení se nezdaří. Můžete kliknout na chyby a upozornění přejít na řádek, kde k nim došlo. Znovu sestavte projekt stisknutím **F7** znovu (znovu zkompilovat pouze soubory s chybami) nebo **Ctrl**+**Alt**+**F7**  (pro vyčištění a úplné opětovné sestavení).

Existují dvě okna s kartami v okně výsledky níže editoru: **výstup** okna, který obsahuje výstup (včetně chybových zpráv); nezpracovaná kompilátoru a **seznam chyb** okno, které poskytuje řazení a filtrování seznamu všechny chyby a upozornění.

Když sestavení proběhne úspěšně, uvidíte výsledky, jako jsou to **výstup** okno:

![Výstup úspěšné sestavení Visual Studia](../ide/media/vs_ide_gs_debug_success_build.png)

## <a name="review-the-error-list"></a>Projděte si seznam chyb

Pokud jste provedli žádné úpravy kódu, který jste dříve a úspěšně sestavili, pravděpodobně jste chybu. Pokud začínáte programování, pravděpodobně máte mnoho z nich. Chyby jsou někdy zřejmé, jako je například Chyba jednoduché syntaxe nebo nesprávný název proměnné a někdy jsou těžko pochopitelné nejasné kód a provede vás. Pro čištění přehled o problémech, přejděte k dolnímu okraji sestavení **výstup** okna a klikněte na **seznam chyb** kartu. Tím přejdete na zobrazení organizovanější chyby a upozornění pro váš projekt a vám dává některé další možnosti.

![Výstup Visual Studia a seznam chyb](../ide/media/vs_ide_gs_debug_bad_build_error_list.png)

Klikněte na řádek s chybou v **seznam chyb** vyvolá se v okně můžete přejít na řádek chybu. (Nebo zapnout čísla řádků kliknutím **Snadné spuštění** řádku v pravém horním rohu, zadáním "čísla řádků" do něj a stisknutím klávesy **Enter**. Toto je nejrychlejší způsob, jak se **možnosti** dialogové okno, ve kterém můžete zapnout čísla řádků. Naučte se používat **Snadné spuštění** pruhové a ušetříte si mnoho uživatelského rozhraní kliknutí!)

![Editor sady Visual Studio s čísly řádků](../ide/media/vs_ide_gs_debug_line_numbers.png)

![Visual Studio čísla řádku](../ide/media/vs_ide_gs_debug_options_line_numbers.png)

Stisknutím klávesy **Ctrl**+**G** rychle přejít k číslu řádku kde došlo k chybě.

Chyba je identifikována red "klikatá" podtržítkem. Najeďte myší nad ním další podrobnosti. Ujistěte se, oprava a jeho přestane být zobrazována, i když zavádíte novou chybu s opravou. (Tomu se říká "regrese".)

![Při najetí myší chyba Visual Studio](../ide/media/vs_ide_gs_debug_error_hover1.png)

Projděte si seznam chyb a vyřešit všechny chyby v kódu.

![Visual Studio ladit chyby okna](../ide/media/vs_ide_gs_debug_error_list.png)

### <a name="review-errors-in-detail"></a>Zkontrolujte chyby v podrobností

Mnoho chyb může žádný smysl pro vás obsahuje jiné spojení jsou v podmínkách kompilátor. V takových případech bude nutné další informace. Z **seznam chyb** okna, můžete provést automatické vyhledávání Bingu Další informace o chybě nebo upozornění. Klikněte pravým tlačítkem na řádku odpovídající položky a vyberte **zobrazit nápovědu k chybě** z místní nabídky nebo klepněte na hodnotu s hypertextovým odkazem chyba kódu v **kód** sloupec **seznam chyb**.

![Visual Studio seznam chyb vyhledávání Bingu](../ide/media/vs_ide_gs_debug_error_list_error_help.png)

V závislosti na nastavení buď ve webovém prohlížeči zobrazí výsledky hledání pro kód chyby a text, nebo na kartě se otevře v sadě Visual Studio a zobrazí výsledky vyhledávání Bingu. Výsledky jsou z mnoha různých zdrojů v Internetu, a nemusí být některé užitečné.

## <a name="use-code-analysis"></a>Použití analýzy kódu

Analyzátorů kódu vyhledejte běžné problémy kódu, které můžou vést k chybám za běhu nebo problémy v kódu správy.

### <a name="c-and-visual-basic-code-analysis"></a>C#a analýza kódu jazyka Visual Basic

Visual Studio obsahuje integrované sady [analyzátory pro .NET Compiler Platform](../code-quality/roslyn-analyzers-overview.md) , zkontrolujte C# a kód jazyka Visual Basic jako vy, zadejte. Jako rozšíření sady Visual Studio, nebo jako balíček NuGet můžete nainstalovat další analyzátory. Pokud se nenajdou porušení pravidel, jsou hlášeny v editoru kódu jako podtržení za problematický kód a **seznam chyb**.

### <a name="c-code-analysis"></a>Analýza kódu C++

Chcete-li provést analýzu kódu C++, spusťte [statickou analýzu kódu](../code-quality/quick-start-code-analysis-for-c-cpp.md). Získejte v podporují ho spustíte, když jste odstranili jasné chyby, které brání úspěšné sestavení a k vyřešení upozornění, který může vytvořit nějakou dobu trvat. Snížíte sami některé obrovskému dolů cestách a dozvíte několik technik styl kódu.

Stisknutím klávesy **Alt**+**F11** (nebo vyberte **analyzovat** > **spustit analýzu kódu na řešení** z hlavní nabídky) do Spusťte analýzu statického kódu.

![Visual Studio Code Analysis položky nabídky](../ide/media/vs_ide_gs_debug_run_code_analysis.png)

Zobrazí všechna upozornění nové nebo aktualizované v **seznam chyb** karta v dolní části rozhraní IDE. Klikněte na upozornění můžete přejít k nim v kódu.

![Seznam chyb sady Visual Studio s upozorněními.](../ide/media/cpp-code-analysis-warning.png)

## <a name="use-quick-actions-to-fix-or-refactor-code"></a>Použít rychlé akce pro opravu nebo refaktorování kódu

[Rychlé akce](../ide/quick-actions.md), která je dostupná z žárovky nebo ikonu šroubovák umožňují Refaktorovat vložený kód. Jsou snadný způsob, jak vyřešit běžné upozornění rychle a efektivně v C#, C++ a Visual Basic code. Pro přístup k nim, klikněte pravým tlačítkem na varování vlnovku a vyberte **rychlé akce a refaktoringy**. Nebo, pokud je kurzor na řádek s barevné vlnovka, stiskněte klávesu **Ctrl**+**.** nebo vyberte žárovky, chyba žárovky nebo šroubovák ikonu na okraji. Zobrazí se vám seznam možných opravy nebo refaktoringů, které můžete provést u tohoto řádku kódu.

![Náhled návrhů Visual Studio](../ide/media/quick-actions-options.png)

Rychlé akce lze použít bez ohledu na to analyzátorů kódu určit, že není příležitost opravit, refaktorace, nebo vylepšení vašeho kódu. Klikněte na libovolném řádku kódu, klikněte pravým tlačítkem na otevřete kontextovou nabídku a vyberte **rychlé akce a refaktoringy**. Refaktoring nebo zlepšování možnosti jsou k dispozici, jsou zobrazeny. V opačném případě zpráva **tady k dispozici žádné rychlé akce** zobrazí v levém dolním rohu integrovaného vývojového prostředí.

![Text k dispozici žádné rychlé akce](../ide/media/vs_ide_gs_debug_light_bulb_no_options.png)

S prostředím, můžete rychle pomocí šipkových kláves a **Ctrl**+**.** ke kontrole snadno refaktoringu příležitosti a vyčistit váš kód!

## <a name="debug-your-running-code"></a>Ladění kódu spuštěného

Teď, právě jste úspěšně vytvořili váš kód a provést trochu čištění, ji spusťte stisknutím kombinace kláves **F5** nebo jeho výběru **ladění** > **spustit ladění**. Tím se spustí vaši aplikaci v prostředí ladění, můžete sledovat jeho chování podrobně. Integrované vývojové prostředí sady Visual Studio změní, když vaše aplikace běží: **výstup** okno nahrazuje dvě nové (ve výchozím okně nastavení), **automatické hodnoty a místní hodnoty/sledování** s kartami okně a **Volání zásobníku zarážky nebo výjimky nebo nastavení/Output** okno s kartami. Tato okna mít několik karet, které vám umožní kontrolovat a vyhodnocovat proměnné vaší aplikace, vlákna, zásobníky volání a různé další chování za běhu.

![Visual Studio automatické hodnoty a Windows zásobníku volání](../ide/media/vs_ide_gs_debug_autos_and_call_stack.png)

Zastavte aplikaci stisknutím klávesy **Shift**+**F5** nebo kliknutím **Zastavit** tlačítko. Nebo můžete jednoduše zavřít hlavní okno aplikace (nebo dialogové okno příkazového řádku).

Pokud váš kód běžel dokonale a přesně tak, jak bylo očekáváno, Blahopřejeme! Ale pokud přestala reagovat, nebo došlo k chybě nebo přiřadil některé strangeová výsledky, bude potřeba vyhledat příčiny těchto problémů a opravit chyby.

### <a name="set-simple-breakpoints"></a>Nastavení jednoduché zarážky

[Zarážky](../debugger/using-breakpoints.md) jsou nejvíce na úrovni basic a essential funkcí spolehlivé ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští. Není nutné znovu sestavit projekt po nastavení a odebrání zarážky.

Nastavit zarážku kliknutím v úplně okraj řádku, kde chcete, aby se zarážka dojít nebo stisknutím klávesy **F9** nastavit zarážku na aktuálním řádku kódu. Při spuštění kódu se pozastaví (nebo *přerušení*) předtím, než se spustí pokyny pro tento řádek kódu.

![Visual Studio zarážku](../ide/media/vs_ide_gs_debug_breakpoint1.png)

Mezi běžná použití pro zarážky patří:

- Abyste omezili příčiny zhroucení nebo zablokování, bodový zarážky v průběhu a ohraničení kódu volání metody, které si myslíte, že je příčinou selhání. Při spuštění kódu v ladicím programu odebrat a současně resetovat zarážce blíže, dokud nenajdete problematický řádek kódu. V části Další informace o spuštění kódu v ladicím programu.

- Když zavádíte nový kód, nastavte zarážku na na začátek a spustit kód, abyste měli jistotu, že se nechová podle očekávání.

- Pokud jste implementovali složité chování, nastavte zarážky pro kód vylepšením tak poškodí program si můžete prohlédnout hodnoty proměnných a data.

- Pokud píšete kód C nebo C++, použijte zarážky pro zastavení kód, takže si můžete prohlédnout hodnoty adres (vyhledejte NULL) a počty odkazů, při ladění chyby související s pamětí.

Další informace o používání zarážek, najdete v článku [pomocí zarážek](../debugger/using-breakpoints.md).

### <a name="inspect-your-code-at-run-time"></a>Kontrola kódu za běhu

Při spuštění kódu narazí na zarážku a je možné, nebyl proveden na řádek kódu, označen žlutou barvou (aktuální příkaz). V tomto okamžiku můžete provést aktuální příkaz a zkontrolujte změněné hodnoty. Můžete použít několik *krok* příkazy ke spouštění kódu v ladicím programu. Pokud volání metody je označené jako kód, můžete krokovat s vnořením ho stisknutím kombinace kláves **F11**. Můžete také *Krokovat přes* řádek kódu stisknutím klávesy **F10**. Další příkazy a podrobnosti o tom, jak krokovat kód, najdete v článku [vyhledání kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).

![Kontroly za běhu hodnotu Visual Studio](../ide/media/vs_ide_gs_debug_hit_breakpoint.png)

V předchozí ilustraci postoupíte příkaz ladicího programu jedním stisknutím klávesy buď **F10** nebo **F11** (protože neexistuje žádná metoda volání, oba příkazy mají stejný výsledek).

Když ladicí program je pozastavený, můžete kontrolovat vaše proměnné a volání zásobníků, chcete-li zjistit, co se děje. Jsou hodnoty v oblasti, které byste měli vidět? Volá se provádějí ve správném pořadí?

![Kontroly za běhu hodnotu Visual Studio](../ide/media/vs_ide_gs_debug_inspect_value.png)

Najeďte myší zobrazíte její aktuální hodnotu a odkazy na proměnnou. Pokud se zobrazí hodnotu, kterou jste neočekávali, pravděpodobně máte chybu v kódu předchozí nebo volání. Další podrobné informace ladění [Další](../debugger/debugger-feature-tour.md) o pomocí ladicího programu.

Kromě toho sada Visual Studio zobrazí **diagnostické nástroje** okno, kde můžete sledovat využití procesoru a paměti vaší aplikace v čase. Později při vývoji aplikace můžete použít tyto nástroje k vyhledání neočekávané náročné využití nebo paměť přidělení procesoru. V kombinaci s **Watch** okna a zarážky, chcete-li zjistit, co je příčinou neočekávané náročné využití nebo nevydané prostředky. Další informace najdete v tématu [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md).

## <a name="run-unit-tests"></a>Spouštění testů jednotek

Testování jednotek je vaší první linie obrany proti kód chyby, proto, že pokud jsou správně provedené, testování jedné "jednotka" kódu, obvykle jednu funkci a usnadňuje ladění než úplné programu. Visual Studio nainstaluje rozhraní testování částí Microsoft pro spravovaný i nativní kód. Použití jednotkových testů vytvořit testy jednotek, spustit je a ohlásí výsledky těchto testů. Pokud provedete změny, k otestování, jestli váš kód stále pracuje správně testů jednotek spusťte znovu. Pomocí sady Visual Studio Enterprise edition je automaticky spustit testy po každém sestavení.

Abyste mohli začít, přečtěte si [generování testů jednotek pro kód pomocí funkce IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).

Další informace o testování částí v sadě Visual Studio a jak vám pomůžou vytvářet lepší kvality kódu, [základní informace o testování částí](../test/unit-test-basics.md).

## <a name="see-also"></a>Viz také:

- [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
- [Další informace o používání ladicího programu](../debugger/debugger-feature-tour.md)
- [Generování a oprava kódu](../ide/code-generation-in-visual-studio.md)