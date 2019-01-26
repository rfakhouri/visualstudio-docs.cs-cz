---
title: Přehled sady Visual Studio pro vývojáře v Pythonu
titleSuffix: ''
ms.date: 12/14/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
dev_langs:
- Python
ms.workload:
- python
- data-science
ms.openlocfilehash: 97b48daf123ea39cd00070fa95c4b488da9d9163
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952948"
---
# <a name="welcome-to-the-visual-studio-ide--python"></a>Vítá vás Visual Studio IDE | Python

Visual Studio *integrovaného vývojového prostředí* je creative odrazový můstek pro Python (a další jazyky), který vám pomůže upravit, ladit, testovat kód a pak publikujete aplikaci. Integrované vývojové prostředí (IDE) je plně funkční program, který lze použít pro mnoho aspektů vývoje softwaru. Nad limit standardní editor a ladicího programu, že většina integrovanými vývojovými prostředími poskytnout, Visual Studio obsahuje doplňování kódu nástroje, interaktivní prostředí REPL, nebo využívat jiné funkce pro usnadnění proces vývoje softwaru.

[![Visual Studio s projektem Python](media/tour-ide-overview.png)](media/tour-ide-overview.png#lightbox)

Tento obrázek ukazuje Visual Studio s otevřeném projektu Pythonu a několika okny nástrojů klíče, které budete pravděpodobně používat:

- [**Průzkumník řešení** ](../ide/solutions-and-projects-in-visual-studio.md) (vpravo nahoře) umožňuje zobrazit, přejděte a spravovat soubory kódu. **Průzkumník řešení** pomáhá organizovat kód seskupením soubory do [řešení a projekty](/visualstudio/get-started/tutorial-projects-solutions).
    - Spolu s **Průzkumníka řešení** je [ **prostředí Pythonu**](managing-python-environments-in-visual-studio.md), kde budete spravovat různé interpretů Pythonu, které jsou nainstalovány ve vašem počítači.

- [Okno editoru](../ide/writing-code-in-the-code-and-text-editor.md) (System center), kde budete pravděpodobně tráví většinu svého času zobrazí obsah souboru. Tady je [úpravy kódu v Pythonu](editing-python-code-in-visual-studio.md), navigace v rámci struktury kódu a nastavit zarážky během relace ladění. S využitím Pythonu, můžete také vybrat kód a stiskněte klávesy Ctrl + Enter pro spuštění tohoto kódu [interaktivního okna REPL](python-interactive-repl-in-visual-studio.md).

- [Okno výstup](../ide/reference/output-window.md) (dole uprostřed) je, kde sada Visual Studio odešle oznámení, jako jsou ladění a chybové zprávy, upozornění, publikování stavové zprávy a další. Každý zdroj zprávy má svůj vlastní kartu.
    - A [okno REPL interaktivní Python](python-interactive-repl-in-visual-studio.md) se zobrazí ve stejné oblasti jako v okně výstup.

- [Team Explorer](/azure/devops/user-guide/work-team-explorer?view=vsts) (vpravo dole) umožňuje sledování pracovních položek a sdílet s ostatními kód pomocí technologie pro řízení verze, například [Git](https://git-scm.com/) a [Team Foundation verze ovládacího prvku (TFVC)](/azure/devops/repos/tfvc/overview?view=vsts).

## <a name="editions"></a>Edice

Visual Studio je k dispozici pro Windows a Mac; Podpora Pythonu je ale dostupná jenom v aplikaci Visual Studio pro Windows.

Existují 3 edicích sady Visual Studio 2017 na Windows: Community, Professional a Enterprise. V tématu [porovnání Visual Studio 2017 integrovanými vývojovými prostředími](https://visualstudio.microsoft.com/vs/compare/) Další informace o funkcích, které jsou podporované v každé edici.

## <a name="popular-productivity-features"></a>Oblíbené pro zvýšení produktivity

Mezi oblíbené funkce v sadě Visual Studio, které vám umožní být produktivnější při vývoji softwaru, patří:

- [IntelliSense](editing-python-code-in-visual-studio.md#intellisense)

   Technologie IntelliSense je termín pro sadu funkcí, která zobrazí informace o kódu přímo v editoru a v některých případech může zapisovat malé části kódu za vás. Je to jako mít základní dokumentaci vložené v editoru, což vám ušetří nebudou muset vyhledat informace o typu jinde. Funkce technologie IntelliSense se liší podle jazyka a [kódu Pythonu úpravy](editing-python-code-in-visual-studio.md#intellisense) článek obsahuje podrobné informace o pro Python. Následující obrázek znázorňuje, jak technologie IntelliSense zobrazí seznam členů pro typ:

   ![Dokončování členů s IntelliSense ve Visual Studio](media/code-editing-completions-simple.png)

- [Refactoring](refactoring-python-code.md)

   Kliknutím pravým tlačítkem na části kódu a výběr **rychlé akce a Refaktoringy**, Visual Studio vám poskytne operace, jako jsou inteligentní přejmenováním proměnné, extrahování jeden nebo více řádků kódu do nové metody, změna pořadí parametrů metod a dalších.

   ![Refaktoring v sadě Visual Studio](media/tour-ide-refactor-extract-method.png)

- [Analyzování kódu](refactoring-python-code.md)

   Linting se kontroluje chyby a problémy v kódu Pythonu můžete podpořit pomocí vhodné Pythonu a vzorů psaní kódu.

   ![Příkaz Pylintu kontextové nabídky pro projekty v Pythonu](media/code-pylint-command.png)

- [Snadné spuštění](../ide/reference/quick-launch-environment-options-dialog-box.md)

   Visual Studio, může to působit příliš složitě čas od času s tolika nabídky, možnosti a vlastnosti. **Snadné spuštění** vyhledávacího pole je skvělý způsob, jak rychle najít, co potřebujete, v sadě Visual Studio. Když začnete psát název něco, co hledáte, Visual Studio obsahuje výsledky, které dostanete, přesně, kde potřebujete přejít. Pokud chcete přidat funkce do sady Visual Studio, například pro přidání podpory pro další programovací jazyk, **Snadné spuštění** poskytuje výsledky, které otevřete instalační program sady Visual Studio k instalaci úloh nebo jednotlivých komponent.

   ![Rychlé spuštění vyhledávacího pole v sadě Visual Studio](media/tour-ide-quick-launch.png)

- Podtržení vlnovkou a [rychlé akce](../ide/quick-actions.md)

   Podtržení vlnovkou jsou podtržení vlnovkou, které vás upozorní na chyby nebo potenciální problémy v kódu při psaní. Tyto vizuální záchytné body umožňují opravit problémy okamžitě bez čekání na chyby mají být zjišťované, a během sestavování nebo při spuštění programu. Pokud najedete myší vlnovka, zobrazí se další informace o této chybě. Žárovky může také zobrazit na levém okraji s akcemi, známé jako rychlých akcí, chcete-li vyřešit chybu.

   ![Podtržení vlnovkou v sadě Visual Studio](media/tour-ide-squiggles.png)

- [Přejít na a náhled definice](../ide/go-to-and-peek-definition.md)

   **Přejít k definici** funkce přejdete přímo do umístění, kde je funkce nebo typ definován. **Definice operace Peek** příkaz zobrazí definici v okně, aniž byste museli otevírat samostatný soubor. **Najít všechny odkazy** příkaz také poskytuje užitečný způsob, jak zjistit, kde jakékoli daným identifikátorem je definovaný i používá.

   ![Příkazy pro navigaci kódu](media/tour-ide-navigation-commands.png)

## <a name="powerful-features-for-python"></a>Výkonné funkce pro Python

- [Interaktivní okno REPL Pythonu](python-interactive-repl-in-visual-studio.md)

    Visual Studio poskytuje oknem interaktivní čtení vyhodnocení print smyčky (REPL) pro každé prostředí Pythonu, které dále to vylepšuje REPL všechno získáte s *python.exe* na příkazovém řádku. V **interaktivní** okně můžete zadat libovolný kód Pythonu a zobrazit výsledky okamžitě.

    ![Interaktivní okno Pythonu](media/interactive-window.png)

- [Ladění](debugging-python-in-visual-studio.md)

    Visual Studio nabízí komplexní možnosti ladění pro Python, včetně připojení ke spuštěným procesům, vyhodnocování výrazů v **Watch** a **okamžité** windows, kontrola místní proměnné, zarážky, krok v/out nebo přes příkazy **nastavit další příkaz**a provádění dalších akcí. Můžete také ladit vzdáleného kódu Pythonu běží na počítače s Linuxem.

    ![Ladění Pythonu v sadě Visual Studio](media/remote-debugging-breakpoint-hit.png)

- [Interakce s C++](working-with-c-cpp-python-in-visual-studio.md)

    Mnoho knihoven, které jsou vytvořené pro Python je napsaný v jazyce C++ pro zajištění optimálního výkonu. Visual Studio poskytuje bohaté funkce pro vývoj rozšíření C++, včetně [ladění ve smíšeném režimu](debugging-mixed-mode-c-cpp-python-in-visual-studio.md).

    ![Ladění ve smíšeném režimu Python a C++ dohromady](media/mixed-mode-debugging.png)

- [Profilace](profiling-python-code-in-visual-studio.md)

    Při použití překladače na základě CPython, můžete vyhodnotit výkon kódu Python v sadě Visual Studio.

    ![Sestava profilace výkonu](media/profiling-results.png)

- [Testování částí](unit-testing-python-in-visual-studio.md)

    Visual Studio poskytuje integrovanou podporu pro zjišťování, spuštěný, a ladění částí vše v rámci rozhraní IDE.

    ![Testování zobrazující stav selhání testu jednotek](media/unit-test-A-fail.png)

## <a name="next-steps"></a>Další kroky

Python v sadě Visual Studio dále prozkoumejte pomocí jednoho z následujících kurzů nebo rychlých startů:

> [!div class="nextstepaction"]
> [Rychlý start: Vytvoření webové aplikace pomocí Flask](../ide/quickstart-python.md?toc=/visualstudio/python/toc.json&bc=/visualstudio/python/_breadcrumb/toc.json)

> [!div class="nextstepaction"]
> [Práce s využitím Pythonu v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

> [!div class="nextstepaction"]
> [Začínáme s webového rozhraní Django v sadě Visual Studio](learn-django-in-visual-studio-step-01-project-and-solution.md)

> [!div class="nextstepaction"]
> [Začínáme s architektury Flask webů v sadě Visual Studio](learn-flask-visual-studio-step-01-project-solution.md)

## <a name="see-also"></a>Viz také:

- Zjistit [další funkce sady Visual Studio](../ide/advanced-feature-overview.md)
- Navštivte [visualstudio.microsoft.com](https://visualstudio.microsoft.com/vs/)
- Čtení [blogu sady Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/)
- Podívejte se na bezplatné kurzy sady Visual Studio na [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!index=2&lang=1033)
