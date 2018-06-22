---
title: Testovací nástroje v sadě Visual Studio Developer
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5cb0899296aa24aa41c0caa2b808b02f27dc80be
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302927"
---
# <a name="developer-testing-tools-scenarios-and-capabilities"></a>Vývojáři, kteří testují nástroje, scénáře a možnosti

Udržujte s testování částí kódu stavu. Visual Studio poskytuje širokou škálu výkonné nástroje a techniky pro vývojáře pro použití při testování aplikací:

## <a name="avoid-regressions-and-achieve-code-coverage-with-intellitest"></a>Vyhněte se regresí a dosáhnout pokrytí kódu pomocí IntelliTest

V tradiční jednotky testovacích sad každý testovacího případu představuje scénářem EXEMPLÁRNÍ využití a kontrolní výrazy obsahují vztah mezi vstupní a výstupní.  Ověření, že spolu s několika takových scénářů může být dost, ale zkušeného vývojáři nachází chyby lurk i v dobře otestované kód, pokud je to správné ale netestované vstupy vyvolat nesprávné odpovědi.

Zlepšení pokrytí a vyhnout se regresí s IntelliTest. IntelliTest výrazně snižuje úsilí nezbytné k vytváření a údržbu testování částí pro nové nebo existující kód.

![IntelliTest v akci](media/devtest-intellitest.png)

* [Úvod do IntelliTest pomocí sady Visual Studio](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20IntelliTest%20with%20Visual%20Studio%20Enterprise%202015.docx)
* [IntelliTest – jeden test pro všechna pravidla](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/05/intellitest-one-test-to-rule-them-all.aspx)
* [IntelliTest videa](https://channel9.msdn.com/Series/Test-Tools-in-Visual-Studio)
* [Začínáme s IntelliTest](generate-unit-tests-for-your-code-with-intellitest.md)
* [Referenční příručka funkce IntelliTest](intellitest-manual/index.md)

## <a name="user-interface-testing-with-coded-ui-and-selenium"></a>Testování pomocí programových uživatelského rozhraní a selenu uživatelského rozhraní

Testování vaší uživatelské rozhraní (UI) s osvědčenými plemene nebo komunity schválených testování uživatelského rozhraní.
Programové testy uživatelského rozhraní poskytují způsob, jak vytvořit plně automatizovaných testů pro ověření chování vaší aplikace uživatelského rozhraní a funkcí.
Jejich můžete automatizovat testování uživatelského rozhraní pro různé technologie, včetně aplikací založených na XAML UWP, prohlížečových aplikací a aplikace služby SharePoint.

Zda zvolíte nejlepší z vyvíjet programových testů uživatelského rozhraní nebo obecné webového uživatelského rozhraní testování pomocí selen, Visual Studio poskytuje všechny nástroje, které potřebujete.

![Uživatelské rozhraní testování pomocí programových uživatelského rozhraní](media/devtest-codeduitest.png)

* [Použití automatizace uživatelského rozhraní k testování kódu](use-ui-automation-to-test-your-code.md)
* [Začínáme vytváření, úpravy a údržba programového testu UI](walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
* [Testování pomocí programových testů uživatelského rozhraní aplikace UWP](test-uwp-app-with-coded-ui-test.md)
* [Testování aplikací služby SharePoint pomocí programových testů uživatelského rozhraní](testing-sharepoint-2010-applications-with-coded-ui-tests.md)
* [Úvod do programové testy uživatelského rozhraní s Visual Studio Enterprise (testovacího prostředí)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20Coded%20UI%20Tests%20with%20Visual%20Studio%20Enterprise%202015.docx)

## <a name="effective-unit-testing-with-visual-studio-code-coverage"></a>Efektivní testování částí pomocí sady Visual Studio pokrytí kódu

Pokud chcete zjistit, jaké části kódu vašeho projektu je ve skutečnosti testuje programové testy, jako je například testy jednotek, můžete použít funkci pokrytí kódu aplikace Visual Studio. Efektivní ochrana proti chyby, by měl testy vykonávat nebo zahrnují velká část kódu.

Analýza pokrytí kódu je použít pro spravované i nespravované (nativní) kódu.

Pokrytí kódu je jedna z možností při spouštění testovacích metod pomocí Průzkumníku testů. Tabulka výsledků zobrazuje procentuální podíl kódu, který byl spuštěn v každém sestavení, třídě a metodě. Editor zdrojového kódu navíc ukazuje samotný kód, který byl testován.

![Testování s Visual Studio Team Services a serveru Team Foundation Server](media/devtest-codecoverage.png)

* [Použití pokrytí kódu k určení, kolik kódu se testuje](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Testování, částí pokrytí kódu a kódu klon analysis pomocí sady Visual Studio (testovacího prostředí)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [Přizpůsobení analýzy pokrytí kódu](customizing-code-coverage-analysis.md)

## <a name="unit-testing-with-any-framework-using-the-high-performance-test-explorer"></a>Testování částí pomocí libovolnou architekturu pomocí vysoký výkon Průzkumníka testů

Otestujte Explorer nápovědy vývojářům vytvářet, spravovat a získat maximální výhody z testování částí.

![Visual Studio Průzkumníka testů](media/devtest-testexplorer.png)

* [Začínáme s testování částí](unit-test-your-code.md)
* [Spouštění testování částí pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md)
* [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)
* [Instalace systémů pro testování částí od třetích stran](install-third-party-unit-test-frameworks.md)

Visual Studio je rozšiřitelný a otevře dveře testování adaptéry například NUnit a xUnit.net částí třetích stran. Kromě toho funkce klonování kódu přejde ruční v dolním s doručováním vysoké kvality softwaru vám pomáhá identifikovat bloky sémanticky podobný kód, který může být kandidáty pro běžné opravy chyb nebo refaktoring.

![Integrace testovací třetích stran](media/devtest-thirdparty.png)

## <a name="see-also"></a>Viz také:

* [Začínáme s testování částí](getting-started-with-unit-testing.md)
* [Urychlení jednotky spuštění testu v produktu Team Foundation Server](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/30/speeding-up-test-execution-in-tfs.aspx)
* [Paralelní a kontext spuštění testu citlivé jednotky](https://blogs.msdn.microsoft.com/visualstudioalm/2016/02/08/parallel-and-context-sensitive-test-execution-with-visual-studio-2015-update-1/)
* [Testování, částí pokrytí kódu a kódu klon analysis pomocí sady Visual Studio (testovacího prostředí)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
