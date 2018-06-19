---
title: Ladění kódu jazyka Python
description: Návod funkce ladění v sadě Visual Studio speciálně pro kód Python, včetně nastavení zarážek, krokování, zkontrolujte hodnoty, prohlížení výjimky a ladění v okně interaktivní.
ms.date: 03/05/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: b521c85bd2a4fb8c29674a51e5e13ded2aba3fec
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32032252"
---
# <a name="debugging-your-python-code"></a>Ladění kódu jazyka Python

Visual Studio nabízí komplexní ladění prostředí Python, včetně připojení ke spuštěným procesům, vyhodnocení výrazů v hodinek a příkazy v nebo na více systémů nebo přes, nastavit další krok okamžitou windows, místní proměnné, zarážky, kontroly Příkaz a další.

Také najdete v následujících článcích ladění konkrétní scénáře:

- [Linux vzdálené ladění](debugging-python-code-on-remote-linux-machines.md)
- [Vzdálené ladění Azure](debugging-remote-python-code-on-azure.md)
- [Ladění ve smíšeném režimu Python/C++](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- [Symboly pro ladění ve smíšeném režimu](debugging-symbols-for-mixed-mode-c-cpp-python.md)

|   |   |
|---|---|
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Debugging-Python-Ep5dp5LWE_3805918567) pro předvedení Python ladění (3 m 32s).|

<a name="debugging-without-a-project"></a>

> [!Tip]
> Python v sadě Visual Studio podporuje ladění bez projektu. Samostatné Python soubor otevřít, klikněte pravým tlačítkem v editoru vybrat **začínat ladění**, a Visual Studio spustí skript s prostředím výchozí globální (najdete v části [prostředí Python](managing-python-environments-in-visual-studio.md)) a žádné argumenty. Ale od toho máte plná podpora ladění.
>
> K řízení prostředí a argumenty, vytvoření projektu pro kód, který je snadno pracovat [z existující Python code](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) šablona projektu.

<a name="debugging-with-a-project"></a>

## <a name="basic-debugging"></a>Základní ladění

Základní pracovní postup ladění zahrnuje nastavení zarážek, krokování kódu, zkontrolujte hodnoty a zpracování výjimek, jak je popsáno v následujících částech.

Ladicí relace začíná **ladění > Spustit ladění** příkaz, **spustit** tlačítka na panelu nástrojů nebo klávesy F5. Tyto akce spuštění vašeho projektu po spuštění souboru (ukazuje tučné v Průzkumníku řešení) se aktivního prostředí projektu a argumenty příkazového řádku nebo cesty pro hledání, které bylo zadáno v okně Vlastnosti projektu (najdete v části [ladění projektu možnosti](#project-debugging-options). **Visual Studio 2017 verze 15,6 operací** a později vás upozorní, pokud nemáte spuštění souboru nastavit; dřívějších verzí může otevřete okno výstup s překladač Pythonu spuštěna, nebo ve výstupním okně stručně se zobrazí a zmizí. V každém případě klikněte pravým tlačítkem na příslušný soubor a vyberte **nastavit jako spouštěcí soubor**.

> [!Note]
> Ladicí program vždy začíná active prostředí Python pro projekt. Chcete-li změnit prostředí, zkontrolujte různých jednu aktivní, jak je popsáno na [výběr prostředí Python pro projekt](selecting-a-python-environment-for-a-project.md).

### <a name="breakpoints"></a>Zarážky

Zarážky zastavit provádění kódu označený okamžiku tak si můžete prohlédnout stav programu. Nastavte zarážky kliknutím na levém okraji editoru kódu nebo kliknutím pravým tlačítkem myši na řádek kódu a výběrem **zarážek > Vložit zarážku**. Na každém řádku s zarážku se zobrazí na červenou tečku.

![Zarážky v sadě Visual Studio](media/debugging-breakpoints.png)

Klikněte na červenou tečku nebo pravým tlačítkem myši na řádek kódu a výběr **zarážek > Odstranit zarážek** odebere zarážku. Můžete ji můžete vypnout bez odebrání pomocí **zarážek > zakázat zarážek** příkaz.

> [!Note]
> Některé zarážky v Pythonu může být překvapivé pro vývojáře, kteří již dříve pracovali s jinými programovací jazyky. V Python celý soubor je spustitelného kódu, takže Python spustí soubor, když je načten do zpracovat všechny třídy nejvyšší úrovně nebo definice funkcí. Pokud byla nastavena na bod přerušení, můžete zjistit ladicího programu narušující třícestné část prostřednictvím deklaraci třídy. Toto chování správné, i když je někdy překvapivé.

Můžete upravit podmínky, za kterých se aktivuje zarážku, jako je například pozastavení jenom v případě, že proměnná je nastavená na hodnotu nebo rozsah hodnot. Chcete-li nastavit podmínky, klikněte pravým tlačítkem myši zarážek červené tečky, vyberte **podmínku**, pak vytvořte výrazy pomocí kód Python. Úplné podrobnosti o této funkci v sadě Visual Studio najdete v tématu [podmínky zarážek](../debugger/using-breakpoints.md#breakpoint-conditions)

Při nastavování podmínky, můžete také nastavit **akce** a vytvořit zprávu do protokolu ve výstupním okně, volitelně pokračování provádění automaticky. Protokolování zprávu vytvoří tzv *tracepoint* bez přidání protokolování kódu do vaší aplikace přímo:

![Vytváření tracepoint s zarážky](media/debugging-tracepoint.png)

### <a name="stepping-through-code"></a>Procházení kódu

Po zastavení na zarážce, máte různé způsoby, jak krok prostřednictvím kódu nebo před porušením znovu spusťte bloky kódu. Tyto příkazy jsou k dispozici v různých místech, včetně nástrojů nejvyšší ladění **ladění** nabídky v místní nabídce klikněte pravým tlačítkem v editoru kódu a pomocí klávesové zkratky (prostřednictvím ne všechny příkazy byly všechny místech):

| Funkce | Klávesová zkratka | Popis |
| --- | --- | --- |
| Pokračovat | F5 | Spustí kód, dokud nebude dosaženo další zarážku. |
| Krok do | F11 | Spustí příkaz Další a zastaví. Pokud příkaz další volání funkce, ladicí program zastaví na prvním řádku volaná funkce. |
| Krok přes | F10 | Spustí příkaz Další, včetně vytváření volání funkce (spuštění všech jeho kódu) a použití žádnou návratovou hodnotu. Krokování s přes umožňuje snadno přeskočit funkce, které není potřeba ladění. |
| Krok | Shift+F11 | Spustí kód až do konce aktuální funkce a potom kroky k volání příkazu.  Tento příkaz je užitečné, když je nebudete muset ladění zbytek aktuální funkce. |
| Spustit ke kurzoru | Ctrl+F10 | Spustí kód až umístění pomocí kurzoru v editoru. Tento příkaz umožňuje snadno přeskočit segment kódu, který je nebudete muset ladění. |
| Nastavit další příkaz | Ctrl+Shift+F10 | Změní aktuální spustit bodu v kódu do umístění souboru pomocí kurzoru. Tento příkaz umožňuje vynechat segment kódu z vůbec spuštěna, například když znáte kód je chybný nebo vytváří a nežádoucí vedlejším účinkem. |
| Zobrazit další příkaz | Alt+Num * | Vrací na další příkaz ke spuštění. Tento příkaz je užitečné, pokud jste vyhledávání ve vašem kódu a nepamatujete, kde je zastavena ladicího programu. |

### <a name="inspecting-and-modifying-values"></a>Kontroly a úpravy hodnot

Když se zastavil v ladicím programu, můžete zkontrolovat a upravit hodnoty proměnných. Okno kukátka také můžete monitorovat jednotlivé proměnné, jakož i vlastní výrazy. (Viz [zkontrolovat proměnné](../debugger/getting-started-with-the-debugger.md#inspect-variables-with-the-autos-and-locals-windows) obecné podrobnosti.)

Chcete-li zobrazit hodnotu pomocí datatips –, jednoduše najeďte myší všechny proměnné v editoru. Kliknutím na hodnotu ho můžete změnit:

![Datatips – v ladicím programu](media/debugging-quick-tips.png)

Okno automobily (**ladění > Windows > automobily**) obsahuje proměnné a výrazy, které již brzy bude dosaženo aktuální příkaz. Můžete dvakrát klikněte ve sloupci Hodnota nebo vybrat a stiskněte klávesu F2 upravte hodnotu:

![Automatické hodnoty – okno v ladicím programu](media/debugging-autos-window.png)

Místní hodnoty – okno (**ladění > Windows > místní hodnoty –**) se zobrazí všechny proměnné, které jsou v aktuálním oboru, který lze upravovat znovu:

![Místní hodnoty – okno v ladicím programu](media/debugging-locals-window.png)

Další informace o používání automobily a místní hodnoty – najdete v tématu [zkontrolujete proměnné v automobily a místní hodnoty – Windows](../debugger/autos-and-locals-windows.md).

Sledování systému windows (**ladění > Windows > sledovat > Podívejte se na 1 – 4**) vám umožní zadat libovolný výrazy jazyka Python a zobrazit výsledky. Výrazy jsou již znovu při každém kroku:

![Kukátko – okno v ladicím programu](media/debugging-watch-window.png)

Další informace o používání sledovat najdete v tématu [nastavení sledování na sledování a QuickWatch Windows proměnné](../debugger/watch-and-quickwatch-windows.md).

Při prohlídce řetězcovou hodnotu (`str`, `unicode`, `bytes`, a `bytearray` jsou zvažovány všechny řetězce pro tento účel), ikonu lupy se zobrazí na pravé straně hodnoty. Kliknutím na ikonu se zobrazí hodnota nekotovaných řetězec v automaticky otevřeném okně dialogu, s zabalení a posouvání obsahu, který je užitečný pro dlouhých řetězců. Kromě toho na tlačítko se šipkou rozevíracího seznamu na ikonu vám umožní vybrat prostý text, HTML, XML a JSON vizualizace:

![Řetězec vizualizérech](media/debugging-string-visualizers.png)

V samostatné místní systém windows pomocí syntaxe zvýrazňování a stromové zobrazení se zobrazí vizualizace HTML, XML a JSON.

### <a name="exceptions"></a>Výjimky

Pokud dojde k chybě v programu během ladění, ale nemáte obslužnou rutinu výjimky pro něj, ladicího programu dělí v okamžiku výjimky:

![Místní nabídka výjimky](media/debugging-exception-popup.png)

V tomto okamžiku si můžete prohlédnout stav programu, včetně zásobníku volání. Ale pokud budete chtít kód krokovat, výjimka pokračuje v hlášeny, dokud se buď zpracovává nebo ji opustí vašeho programu.

**Ladění > Windows > Nastavení výjimky** příkazu v nabídce otevře okno, ve kterém můžete rozšířit **Python výjimky**:

![Okno výjimky](media/debugging-exception-settings.png)

Zaškrtávací políčko pro každý ovládací prvky výjimka zda ladicího programu *vždy* dělí, když je aktivována. Toto políčko zaškrtněte, pokud chcete rozdělit častěji pro konkrétní výjimku.

Ve výchozím nastavení většina výjimek přerušení při obslužnou rutinu výjimky nebyl nalezen ve zdrojovém kódu. Toto chování změnit, klikněte pravým tlačítkem na jakékoli výjimky a upravovat **pokračovat v případě neošetřené v uživatelském kódu** možnost. Pokud chcete rozdělit méně často pro výjimku, zrušte zaškrtnutí tohoto políčka.

Chcete-li konfigurovat výjimku, které nejsou uvedené v tomto seznamu, klikněte na tlačítko **přidat** tlačítko Přidat. Název musí odpovídat názvu úplné výjimky.

## <a name="project-debugging-options"></a>Možnosti ladění projektu

Ve výchozím nastavení spustí ladicí program vašeho programu standardní Spouštěč jazyka Python, žádné argumenty příkazového řádku a žádné jiné speciální cesty a podmínky. Možnosti spuštění došlo ke změně prostřednictvím vlastnosti ladění projektu přístup kliknutím pravým tlačítkem na projekt v Průzkumníku řešení, výběr **vlastnosti**a výběr **ladění** kartě.

![Vlastnosti ladění projektu](media/debugging-project-properties.png)

### <a name="launch-mode-options"></a>Spuštění režimu možnosti

| Možnost | Popis |
| --- | --- |
| Standardní Spouštěč jazyka Python | Využívá ladění kód napsaný v přenosných Python, který je kompatibilní s CPython IronPython a variant například Stackless Python. Poskytuje dosažení co nejlepších výsledků pro ladění čistý kód Python. Když připojíte k spuštěný `python.exe` procesy, se používá tato Spouštěče. Také poskytuje tento spouštěč [ladění ve smíšeném režimu](debugging-mixed-mode-c-cpp-python-in-visual-studio.md) pro CPython, což umožňuje krok bezproblémově mezi kódu C/C++ a kód Python. |
| Spouštěč webových | Spustí výchozí prohlížeč při spuštění a povolí ladění šablon. Najdete v článku [ladění webové šablony](python-web-application-project-templates.md#debugging) části Další informace. |
| Spouštěč webových rozhraní Django | Identické Spouštěč webových a zobrazeno pouze pro zpětné kompatibility. |
| Spouštěč IronPython (.NET) | Ladicí program rozhraní .NET, která pracuje pouze s IronPython používá ale umožňuje krokování mezi žádným projektem jazyk rozhraní .NET, včetně C# a VB. Pokud připojíte k spuštěných procesů .NET, který je hostitelem IronPython, použije se tento Spouštěče. |

### <a name="run-options-search-paths-startup-arguments-and-environment-variables"></a>Spustit možnosti (cesty hledání, spuštění argumentů a proměnných prostředí)

| Možnost | Popis |
| --- | --- |
| Cesty hledání | Tyto hodnoty odpovídat, co se zobrazí v uzlu projektu cesty hledání v Průzkumníku řešení. Tato hodnota zde můžete upravit, ale je snazší pomocí Průzkumníka řešení, která vám umožňuje procházet složky a automaticky převede na formulář relativní cesty. |
| Argumenty skriptu | Tyto argumenty se přidají do příkaz použitý ke spuštění skriptu, zobrazování po filename vašeho skriptu. První položky v tomto poli je k dispozici pro váš skript jako `sys.argv[1]`, druhý jako `sys.argv[2]`a tak dále. |
| Překladač argumenty | Tyto argumenty se přidají do příkazového řádku Spouštěče před název souboru skriptu. Jsou zde běžné argumenty `-W ...` na ovládací prvek upozornění, `-O` mírně optimalizace programu, a `-u` používat vstupně-výstupní operace bez vyrovnávací paměti. Uživatelé IronPython je pravděpodobné, že použití tohoto pole k předání `-X` možnosti, jako například `-X:Frames` nebo `-X:MTA`. |
| Překladač cesta | Přepíše cesta přidružená aktuální prostředí.  Hodnota může být užitečné pro spouštění vašeho skriptu s nestandardní překladač. |
| Proměnné prostředí | V tomto poli víceřádkový text, přidat položky ve formátu `NAME=VALUE`. Protože toto nastavení je použito jako poslední, v horní části všechny stávající globální proměnné a po `PYTHONPATH` je nastaven podle nastavení cesty hledání ji umožňuje ručně přepsat všechny z nich jiné proměnné. |

<a name="the-debug-interactive-window"></a>

## <a name="immediate-and-interactive-windows"></a>Okamžité a interaktivní windows

Existují dvě interaktivní windows můžete během relace ladění: okno Standardní okamžitou Visual Studio a Python ladění interaktivních okna.

Příkazové podokno (**ladění > Windows > Immediate**) slouží k přiřazení proměnných v rámci spuštěným programem nebo rychlé vyhodnocení výrazů jazyka Python a kontroly. Najdete v části Obecné [hodnot proměnných](../ide/reference/immediate-window.md) článku.

Okno Python ladění interaktivní (**ladění > Windows > Python ladění interaktivní**) je širší, protože umožňuje kompletní [interaktivní REPL](python-interactive-repl-in-visual-studio.md) dojde k dispozici při ladění, včetně zápis a spuštění kódu. Automaticky připojí se k žádné proces spuštěný v ladicím programu pomocí standardní Python Spouštěče (včetně procesy připojená prostřednictvím **ladění > připojit k procesu**). Není, ale k dispozici při použití ladění ve smíšeném režimu C/C++.

![Python ladění interaktivních okna](media/debugging-interactive.png)

Ladění interaktivních okna podporuje speciální meta příkazy kromě [standardní příkazy REPL](python-interactive-repl-in-visual-studio.md#meta-commands):

| Příkaz | Arguments | Popis |
| --- | --- | --- |
| `$continue`, `$cont`, `$c` | Spuštění programu z aktuální příkaz. |
| `$down`, `$d` | Přesunete aktuální rámec jednu úroveň níže v trasování zásobníku. |
| `$frame` | | Zobrazí aktuální id rámce.
| `$frame` | id rámce | Přepne do zadaného rámce id aktuálního snímku.
| `$load` | Načte příkazy ze souboru a provede až do dokončení |
| `$proc` |  | Zobrazí aktuální id procesu. |
| `$proc` | Id procesu | Aktuální proces se přepne do id zadaný procesu. |
| `$procs` | | Zobrazí seznam procesů, které jsou právě laděn. |
| `$stepin`, `$step`, `$s` | Kroky do další volání funkce, pokud je to možné. |
| `$stepout`, `$return`, `$r` | Kroky mimo aktuální funkce. |
| `$stepover`, `$until`, `$unt` | Kroky přes další volání funkce. |
| `$thread` | | Zobrazí aktuální id vlákna. |
| `$thread` | Id podprocesu | Aktuální vlákno se přepne do id zadaný vlákna. |
| `$threads` | | Uvádí vláken právě laděn. |
| `$up`, `$u` | | Aktuální úroveň jeden rámeček přesunete nahoru v trasování zásobníku. |
| `$where`, `$w`, `$bt` | Uvádí rámce pro aktuální vlákno. |

Všimněte si, že standardní ladicího programu, například procesy, vláken a zásobníkem volání nejsou synchronizované s ladění interaktivních okna. Změna aktivní proces, vlákno nebo rámce v okně ladění interaktivní nemá vliv na ostatní ladicího programu. Změna aktivní proces, vlákno nebo rámce v ladicího programu podobně neovlivní ladění interaktivních okna.

Ladění interaktivních okna má vlastní sadu možností, které můžete přistupovat prostřednictvím **nástroje > Možnosti > Python Tools > ladění interaktivních okna**. Na rozdíl od regulární Python interaktivních okna, která má samostatnou instanci pro každé prostředí Python, existuje pouze jeden ladění interaktivních okna a vždy používá překladač Pythonu pro proces laděné. V tématu [možnosti - možnosti ladění](python-support-options-and-settings-in-visual-studio.md#debugging-options).

![Ladění interaktivní okno Možnosti](media/debugging-interactive-options.png)

## <a name="see-also"></a>Viz také

Kompletní informace o ladicího programu sady Visual Studio, najdete v části [ladění v sadě Visual Studio](../debugger/debugger-feature-tour.md).