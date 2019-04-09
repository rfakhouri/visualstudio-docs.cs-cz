---
title: Podpora Pythonu v sadě Visual Studio ve Windows
titleSuffix: ''
description: Přehled funkce Pythonu v sadě Visual Studio, takže nejlepší prostředí Python IDE ve Windows (označované také jako Python Tools for Visual Studio, PTVS).
ms.date: 03/12/2019
ms.topic: overview
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 2c6e17b0556b324e0dde6fe188b9d21efb542778
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59366871"
---
# <a name="work-with-python-in-visual-studio-on-windows"></a>Práce s využitím Pythonu v sadě Visual Studio ve Windows

Python je oblíbený programovací jazyk, který je spolehlivé, flexibilní, snadno se jej naučíte, bezplatné použití ve všech operačních systémech a podporovaná smlouvou do komunity vývojářů silné a free mnoho knihoven. Python podporuje všechny způsoby vývoje, včetně webových aplikací, webových služeb, aplikací klasické pracovní plochy, skriptování a vědecké výpočty a používá mnoho univerzity, odborníky, příležitostné vývojáři a nabídne profesionální vývojáři. Další informace o jazyku na [python.org](https://www.python.org) a [Python pro začátečníky](https://www.python.org/about/gettingstarted/).

Visual Studio je výkonné prostředí IDE Python ve Windows. Visual Studio poskytuje [open source](https://github.com/Microsoft/ptvs) podporu jazyka Python pomocí **vývoj v jazyce Python** a **pro datovou vědu** úlohy (Visual Studio 2017 a novější) a bezplatné nástroje Pythonu pro Visual Studio rozšíření (Visual Studio 2015 a starší).

Python v současné době nepodporuje v sadě Visual Studio pro Mac, ale je k dispozici na Mac a Linux přes Visual Studio Code (viz [otázek a odpovědí](#questions-and-answers)).

Jak začít:

- Postupujte podle [pokyny k instalaci](installing-python-support-in-visual-studio.md) nastavit úlohou Pythonu.
- Seznámíte se s funkcemi Python sady Visual Studio si části v tomto článku.
::: moniker range="vs-2017"
- Projděte si jeden nebo více šablon rychlý start k vytvoření projektu. Pokud si nejste jisti, začněte tématem [vytvoření webové aplikace pomocí Flask](../ide/quickstart-python.md?toc=/visualstudio/python/toc.json&bc=/visualstudio/python/_breadcrumb/toc.json).
::: moniker-end
::: moniker range=">=vs-2019"
- Projděte si jeden nebo více šablon rychlý start k vytvoření projektu. Pokud si nejste jisti, začněte tématem [rychlý start: Otevření a spuštění kódu Pythonu ve složce](quickstart-05-python-visual-studio-open-folder.md) nebo [vytvoření webové aplikace pomocí Flask](../ide/quickstart-python.md?toc=/visualstudio/python/toc.json&bc=/visualstudio/python/_breadcrumb/toc.json).
::: moniker-end
- Postupujte podle [pracovat s využitím Pythonu v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md) kurzu pro prostředí úplného začátku do konce.

## <a name="support-for-multiple-interpreters"></a>Podpora pro více interprety

Visual Studio **prostředí Pythonu** okno (viz následující obrázek v široké, rozšířené zobrazení) poskytuje jednotné místo, kde můžete spravovat všechny globální prostředí Pythonu, prostředí conda a virtuální prostředí. Visual Studio automaticky zjišťuje instalace Pythonu ve standardní umístění a umožňuje nakonfigurovat vlastní zařízení. Každé prostředí můžete snadno spravovat balíčky, otevřete interaktivní okno pro toto prostředí a přístup ke složkám na prostředí.

::: moniker range="vs-2017"
![Rozšířené zobrazení okno prostředí Pythonu](media/environments/environments-expanded-view.png)
::: moniker-end
::: moniker range=">=vs-2019"
![Rozšířené zobrazení okno prostředí Pythonu](media/environments/environments-expanded-view-2019.png)
::: moniker-end

Použití **otevřít interaktivní okno** příkaz interaktivní spuštění Pythonu v rámci sady Visual Studio. Použití **otevřít v PowerShell** příkaz pro otevření okna samostatný příkaz ve složce vybraného prostředí. Z tohoto okna Příkazový skript můžete spustit všechny python.

Další informace:

- [Správa prostředí Pythonu](managing-python-environments-in-visual-studio.md)
- [Odkaz na prostředí Pythonu](python-environments-window-tab-reference.md)

## <a name="rich-editing-intellisense-and-code-comprehension"></a>Bohaté možnosti úpravy, technologii IntelliSense a porozumění kódu

Visual Studio poskytuje prvotřídní editor Pythonu, včetně barevné zvýrazňování syntaxe, automatické dokončování kódu a knihoven, formátování, signaturám, refaktoring, linting a typu kódu. Visual Studio také poskytuje jedinečné funkce, jako je zobrazení tříd **přejít k definici**, **najít všechny odkazy**a fragmenty kódu. Přímá integrace s [interaktivní okno](#interactive-window) vám pomůže rychle vytvořit kód Pythonu, který je již uložen v souboru.

![Dokončování kódu pro kód Python v sadě Visual Studio](media/code-editing-completions-simple.png)

Další informace:

- Dokumentace: [Úpravy kódu v Pythonu](editing-python-code-in-visual-studio.md)
- Dokumentace: [Formátovat kód](formatting-python-code.md)
- Dokumentace: [Refaktorování kódu](refactoring-python-code.md)
- Dokumentace: [Použít linter](linting-python-code.md)
- Visual Studio – Obecné funkce dokumentace: [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)

## <a name="interactive-window"></a>Interaktivní okno

Pro všechna prostředí Pythonu, známé sady Visual Studio můžete jednoduše otevřít stejné interaktivního prostředí (REPL) pro interpret Pythonu přímo v rámci sady Visual Studio, spíš než samostatném příkazovém řádku. Můžete snadno přepínat mezi prostředími také. (Otevřete samostatném příkazovém řádku, vyberte požadované prostředí v **prostředí Pythonu** okna, vyberte **otevřít v PowerShell** příkaz, jak je vysvětleno výše v části [podpory u více interpretů](#support-for-multiple-interpreters).)

![Interaktivní okno Pythonu v sadě Visual Studio](media/interactive-window.png)

Visual Studio také nabízí úzkou integraci mezi editor kódu Python a **interaktivní** okna. **Ctrl**+**Enter** klávesové zkratky pohodlně odešle aktuální řádek v editoru kódu (nebo blok kódu) **interaktivní** okno, pak přesune na další řádek (nebo blok). **CTRL**+**Enter** vám umožní snadno procházejte kódem po krocích bez nutnosti spuštění ladicího programu. Můžete také odeslat vybraný kód do **interaktivní** okna se stejnou stisknutí kláves a snadno vložte kód z **interaktivní** okno do editoru. Společně tyto funkce umožňují zjistit podrobnosti pro segment kódu **interaktivní** okno a snadno uložit výsledky do souboru v editoru.

Visual Studio také podporuje IPython/Jupyter v REPL, včetně vložené grafy, .NET a Windows Presentation Foundation (WPF).

Další informace:

- [Interaktivní okno](python-interactive-repl-in-visual-studio.md)
- [IPython v sadě Visual Studio](interactive-repl-ipython.md)

## <a name="project-system-and-project-and-item-templates"></a>Systém projektů a šablon projektů a položek

::: moniker range=">=vs-2019"
> [!Note]
> Visual Studio 2019 podporuje otevření složky obsahující kód v Pythonu a spuštění tohoto kódu bez vytvoření souborů projektu a řešení sady Visual Studio. Další informace najdete v tématu [rychlý start: Otevření a spuštění kódu Pythonu ve složce](quickstart-05-python-visual-studio-open-folder.md). Existují však výhody použití souboru projektu, jak je popsáno v této části.
::: moniker-end

Visual Studio vám pomůže spravovat složitosti projektu roste v čase. A *projektu sady Visual Studio* je mnohem víc než strukturu složek: zahrnuje pochopení různých souborů se používají a jejich vzájemné vztahy mezi sebou. Visual Studio umožňuje rozlišovat kód aplikace, testování kódu, webové stránky, JavaScript, skripty sestavení a tak dále, které pak povolte funkce odpovídající soubor. Řešení sady Visual Studio navíc umožňuje spravovat několik souvisejících projektů, jako je Python projektu a projekt rozšíření jazyka C++.

![Visual Studio řešení obsahující projekty Python a C++](media/projects-solution-explorer-two-projects.png)

Šablony projektů a položek automatizaci procesu nastavení různé typy projektů a souborů, šetří cenný čas a homogenního vám od správy podrobnosti složité a náchylné k chybě. Visual Studio poskytuje šablony pro web, Azure, datové vědy, konzoly a jiné typy projektů, spolu s šablony pro soubory, jako třídy, testy jednotek, konfigurace Azure web, HTML a dokonce i aplikace Django Python.

[![Pythonu šablony projektu a položky v sadě Visual Studio](media/project-and-item-templates.png)](media/project-and-item-templates.png#lightbox)

Další informace:

- Dokumentace: [Správa projektů v Pythonu](managing-python-projects-in-visual-studio.md)
- Dokumentace: [Referenční informace pro položku šablony](python-item-templates.md)
- Dokumentace: [Šablony projektů v Pythonu](managing-python-projects-in-visual-studio.md#project-templates)
- Dokumentace: [Práce s C++ a Python](working-with-c-cpp-python-in-visual-studio.md)
- Visual Studio – Obecné funkce dokumentace: [Šablony projektů a položek](../ide/creating-project-and-item-templates.md#visual-studio-templates)
- Visual Studio – Obecné funkce dokumentace: [Řešení a projekty v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)

## <a name="full-featured-debugging"></a>Plně vybavené ladění

Jednou z Visual Studio předností je jeho výkonný ladicí program. Pro jazyk Python, Visual Studio zahrnuje zejména Python/C++ ve smíšeném režimu ladění, vzdálené ladění na Linuxu, ladění v rámci **interaktivní** okno a ladění testů jednotek v Pythonu.

![Ladicí program sady Visual Studio pro Python k výjimce automaticky otevírané okno zobrazující](media/debugging-exception-popup.png)

::: moniker range=">=vs-2019"
V aplikaci Visual Studio 2019 můžete spustit a ladit kód bez nutnosti soubor projektu sady Visual Studio. Zobrazit [rychlý start: Otevření a spuštění kódu Pythonu ve složce](quickstart-05-python-visual-studio-open-folder.md) příklad.
::: moniker-end

Další informace:

- Dokumentace: [Ladění Pythonu](debugging-python-in-visual-studio.md)
- Dokumentace: [Ladění ve smíšeném režimu Python/C++](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- Dokumentace: [Vzdálené ladění na Linuxu](debugging-python-code-on-remote-linux-machines.md)
- Visual Studio – Obecné funkce dokumentace: [Prohlídka funkcí ladicího programu sady Visual Studio](../debugger/debugger-feature-tour.md)

## <a name="profiling-tools-with-comprehensive-reporting"></a>Nástroje pro profilaci s komplexní vykazování

Profilace zkoumá, jak je právě doba trvání v rámci vaší aplikace. Visual Studio podporuje profilace se na základě CPython interprety a nabízí možnost k porovnání výkonu mezi během různých spuštění profilování.

[![VVisual Studio profiler výsledky projektu Pythonu](media/profiling-results.png)](media/profiling-results.png#lightbox)

Další informace:

- Dokumentace: [Python nástroje pro profilaci](profiling-python-code-in-visual-studio.md)
- Visual Studio – Obecné funkce dokumentace: [Průvodce funkcí profilování](../profiling/profiling-feature-tour.md). (Ne všechny funkce pro profilaci sady Visual Studio jsou k dispozici pro Python).

## <a name="unit-testing-tools"></a>Nástroje testování částí

Zjišťování, spouštět a spravovat testy v sadě Visual Studio **Průzkumník testů**a snadno ladit testy jednotek.

![Ladění test jednotky Pythonu v sadě Visual Studio](media/unit-test-debugging.png)

Další informace:

- Dokumentace: [Nástroje testování částí pro Python](unit-testing-python-in-visual-studio.md)
- Visual Studio – Obecné funkce dokumentace: [Testování částí kódu](../test/unit-test-your-code.md).

## <a name="azure-sdk-for-python"></a>Azure SDK pro Python

Úlohy Python obsahuje sadu Azure SDK pro Python, která zjednodušuje využívání služeb Azure z aplikace pro Windows, Mac OS X a Linux.

Další informace najdete v tématu [sady Azure SDK for Python](/python/azure/?view=azure-python).

## <a name="questions-and-answers"></a>Otázky a odpovědi

**Otázka: Nabízíme podporu Pythonu pomocí sady Visual Studio for Mac?**

A. Není v tuto chvíli ale žádost až můžete hlasovat o [komunity vývojářů](https://developercommunity.visualstudio.com/content/idea/351820/python-tools-for-visual-studio-mac.html). [Visual Studio for Mac](/visualstudio/mac/) dokumentaci identifikuje aktuální typy vývoje, který podporuje. Do té doby, Visual Studio Code ve Windows, Mac a Linux [dobře funguje pro Python prostřednictvím rozšíření k dispozici](https://code.visualstudio.com/docs/languages/python).

**Otázka: Co je můžete použít k vytvoření uživatelského rozhraní pomocí Pythonu?**

A. Hlavní nabídka v této oblasti je [Qt projektu](https://www.qt.io/qt-for-application-development/), s vazbami pro Python, označované jako [PySide (oficiální vazby)](https://wiki.qt.io/PySide) (také naleznete v tématu [PySide stáhne](https://download.qt.io/official_releases/pyside/.)) a [ PyQt](https://wiki.python.org/moin/PyQt). V současné době podpora Pythonu v sadě Visual Studio neobsahuje žádné konkrétní nástroje pro vývoj uživatelského rozhraní.

**Otázka: Projektu Pythonu může vytvořit samostatný spustitelný soubor?**

A. Python je obecně interpretovaný jazyk, se kterým je kód spuštěn na vyžádání v vhodné podporující Python prostředí, jako je Visual Studio a webové servery. Samotné sady Visual Studio v současné době neposkytuje způsob, jak vytvořit samostatný spustitelný soubor, který v podstatě znamená, že program s vložený interpret Pythonu. Python komunity, však poskytnuty jiný způsob, jak vytvořit spustitelné soubory, jak je popsáno v [StackOverflow](https://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython také podporuje se vložený do nativní aplikace, jak je popsáno v blogovém příspěvku [soubor zip Vložitelný pomocí CPython](https://devblogs.microsoft.com/python/cpython-embeddable-zip-file/).

::: moniker range="<=vs-2017"

## <a name="feature-support"></a>Podpora funkce

Funkce Pythonu můžete nainstalovat v následujících edicích sady Visual Studio, jak je popsáno v [Průvodce instalací](installing-python-support-in-visual-studio.md):

- [Visual Studio 2019 (všechny edice)](https://visualstudio.microsoft.com/vs/)
- Visual Studio 2017 (všechny edice)
- Visual Studio 2015 (všechny edice)
- Visual Studio 2013 Community Edition
- Visual Studio Express 2013 for Web, s aktualizací Update 2 nebo vyšší
- Visual Studio 2013 Express for Desktop, s aktualizací Update 2 nebo vyšší
- Visual Studio 2013 (verze Pro vydání nebo novější)
- Visual Studio 2012 (Pro edice nebo vyšší)
- Visual Studio 2010 SP1 (edice Pro nebo vyšší; vyžaduje .NET 4.5)

Jsou k dispozici v sadě Visual Studio 2015 a starší [visualstudio.microsoft.com/vs/older-downloads/](https://visualstudio.microsoft.com/vs/older-downloads/).

> [!Important]
> Funkce jsou plně podporované a udržovat jenom nejnovější verze sady Visual Studio. Funkce jsou k dispozici ve starších verzích ale nejsou aktivně spravovány.

|          Podpora jazyka Python          |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|----------------------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
|   Správa více interprety   | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| Automatické rozpoznání oblíbených interprety | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|     Přidat vlastní interprety      | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|       Virtuální prostředí       | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|         PIP a snadná instalace         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|         Systém projektu         |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + |      2012 pro +       | 2010 SP1 Pro + |
|--------------------------------|----------|----------|-----------|--------------|----------|-----------|----------------------|---------------|
| Nový projekt z existujícího kódu | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  |       &#10004;       |   &#10004;    |
|         Zobrazit všechny soubory         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  |       &#10004;       |   &#10004;    |
|         Správy zdrojového kódu         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  |       &#10004;       |   &#10004;    |
|        Integrace Gitu         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;<sup>1</sup> |   &#10007;    |

<br/>


|           Úpravy            |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|------------------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
|     Zvýrazňování syntaxe      | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|        Automatické dokončování         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|        Nápověda k podpisu        | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|          Rychlé informace          | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|  Zobrazení třídy a prohlížeče objektů   | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|        Navigační panel        | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|       Přejít k definici       | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|         Přejděte na          | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|     Najít všechny odkazy      | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|       Automatické odsazení       | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|       Formátování kódu        | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|      Refaktorovat – přejmenovat       | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|  Refaktorovat – extrahování metody   | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| Refaktorovat – přidání nebo odebrání importu | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|            Pylintu            | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|     Interaktivní okno     |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|----------------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
|     Interaktivní okno     | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| IPython vložené grafů | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|               Desktop               |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|-------------------------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
|     Aplikace konzoly/Windows     | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| WPF v Ironpythonu (pomocí návrháře XAML) | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|      IronPython Windows Forms       | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|         Web         |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|---------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
| Webový projekt Django  | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| Bottle webového projektu  | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|  Webový projekt Flask  | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
| Obecný webový projekt | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|         Azure          |   2017+   |   2015   | Potvrd 2013 | 2013 desktop |       2013 web       |      Pro 2013 +       |      2012 pro +       |    2010 SP1 Pro +     |
|------------------------|----------|----------|-----------|--------------|----------------------|----------------------|----------------------|----------------------|
|   Nasazení na web   | &#10004; | &#10004; | &#10004;  |   &#10007;   |       &#10004;       |       &#10004;       |       &#10004;       | &#10004;<sup>2</sup> |
|   Nasazení do webové role   | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> |       &#10007;       |
| Nasazení do role pracovního procesu  |    ?     |    ?     |     ?     |   &#10007;   | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> |       &#10007;       |
| Spustit v emulátoru Azure  |    ?     |    ?     |     ?     |   &#10007;   | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> |       &#10007;       |
|    Vzdálené ladění    | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> |       &#10007;       |
| Připojení Průzkumníka serveru | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> |       &#10007;       |       &#10007;       |

<br/>


|           Šablony Django           |   2017+   |   2015   | Potvrd 2013 | 2013 desktop |       2013 web       |      Pro 2013 +       | 2012 pro + | 2010 SP1 Pro + |
|--------------------------------------|----------|----------|-----------|--------------|----------------------|----------------------|-----------|---------------|
|              Ladění               | &#10004; | &#10004; | &#10004;  |   &#10007;   |       &#10004;       |       &#10004;       | &#10004;  |   &#10004;    |
|            Automatické dokončování             | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004;  |   &#10004;    |
| Automatické dokončování pro šablony stylů CSS a JavaScript | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007;  |   &#10007;    |

<br/>


|                  Ladění                  |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|---------------------------------------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
|                  Ladění                  | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|         Ladění bez projektu         | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |
|        Ladění – připojení k úpravám        | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10007; | &#10004;  | &#10004;  |   &#10004;    |
|            Ladění ve smíšeném režimu             | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10007;    |
| Vzdálené ladění (Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10007; | &#10004;  | &#10004;  |   &#10004;    |
|          Interaktivní okno ladění           | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10004;    |

<br/>

<a name="matrix-profiling"></a>


| Profilace |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|-----------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
| Profilace | &#10004; | &#10004; | &#10004;  |   &#10007;   | &#10007; | &#10004;  | &#10004;  |   &#10004;    |

<br/>


|     Test      |   2017+   |   2015   | Potvrd 2013 | 2013 desktop | 2013 web | Pro 2013 + | 2012 pro + | 2010 SP1 Pro + |
|---------------|----------|----------|-----------|--------------|----------|-----------|-----------|---------------|
| Průzkumník testů | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10007;    |
|   Spuštění testu    | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10007;    |
|  Ladit test   | &#10004; | &#10004; | &#10004;  |   &#10004;   | &#10004; | &#10004;  | &#10004;  |   &#10007;    |

<br/>

1. Podpora pro Git pro sadu Visual Studio 2012 je k dispozici v nástrojích Visual Studio Tools pro rozšíření Git, k dispozici na [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=TFSPowerToolsTeam.VisualStudioToolsforGit).

1. Nasazení na webu Azure vyžaduje [sady Azure SDK pro .NET 2.1 – Visual Studio 2010 SP1](https://go.microsoft.com/fwlink/?LinkId=313855). Novější verze sady Visual Studio 2010 nepodporují.

1. Podpora pro Azure Web Role a Role pracovního procesu vyžaduje [sady Azure SDK for .NET 2.3 – VS 2012](https://go.microsoft.com/fwlink/?LinkId=323511) nebo novější.

1. Podpora pro Azure Web Role a Role pracovního procesu vyžaduje [sady Azure SDK for .NET 2.3 – VS 2013](https://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Editor šablon Django v sadě Visual Studio 2013 obsahuje některé známé problémy, které se vyřeší instalací aktualizace 2.

1. Vyžaduje systém Windows 8 nebo novější. Visual Studio Express 2013 for Web nemá **připojit k procesu** dialogového okna, ale Azure webového serveru vzdálené ladění je stále možné pomocí **připojit ladicí program (Python)** v příkaz **serveru Průzkumník**. Vzdálené ladění vyžaduje [sady Azure SDK for .NET 2.3 – Visual Studio 2013](https://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Vyžaduje systém Windows 8 nebo novější. **Připojit ladicí program (Python)** v příkaz **Průzkumníka serveru** vyžaduje [sady Azure SDK for .NET 2.3 – Visual Studio 2013](https://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

1. Vyžaduje systém Windows 8 nebo novější.
::: moniker-end
