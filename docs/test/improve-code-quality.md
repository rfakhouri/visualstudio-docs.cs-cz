---
title: Testovací nástroje
ms.date: 03/16/2018
ms.topic: conceptual
helpviewer_keywords:
- testing tools [Visual Studio]
- unit tests [Visual Studio]
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 435eb2571f709f3ed5df4effbfdf3b5f4970457b
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461400"
---
# <a name="testing-tools-in-visual-studio"></a>Testovací nástroje v sadě Visual Studio

Testovací nástroje sady Visual Studio vám může pomoct a váš tým vyvíjet a udržovat vysoké standardy pro vzdělávání profesionálů v oblasti kódu.

> [!NOTE]
> Testování jednotek je k dispozici ve všech edicích sady Visual Studio. Další testovací nástroje, jako je Live Unit Testing, Intellitestu a programový Test uživatelského rozhraní jsou dostupné jenom v edici Visual Studio Enterprise. Další informace o vydáních najdete v části [porovnání prostředí IDE Visual Studio](https://visualstudio.microsoft.com/vs/compare/).

## <a name="test-explorer"></a>Průzkumník testů

**Průzkumník testů** okno pomáhá vývojářům vytvářet, spravovat a spouštět testy jednotek. Můžete použít rozhraní testování částí Microsoft nebo jeden z několika rámců třetích stran a open source.

![Průzkumník testů sady Visual Studio](media/devtest-testexplorer.png)

* [Začínáme s testováním částí](unit-test-your-code.md)
* [Spouštění testování částí pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md)
* [Průzkumník testů – nejčastější dotazy](test-explorer-faq.md)
* [Instalace systémů pro testování částí od třetích stran](install-third-party-unit-test-frameworks.md)

Visual Studio je rozšiřitelné a otevře dveře pro adaptéry jako například NUnit a xUnit.net testování jednotky třetí strany. Kromě toho přejde funkce klonování kódu ručně spolupráce s doručování vysoce kvalitního softwaru díky tomu můžete identifikovat bloky sémanticky podobné kódu, který se může jednat o kandidáty na běžné opravy chyby nebo refaktoring.

![Integrace testování třetích stran](media/devtest-thirdparty.png)

## <a name="live-unit-testing"></a>Live Unit Testing

[Live Unit Testing](../test/live-unit-testing.md) automaticky spustí testy jednotek na pozadí a graficky zobrazuje výsledky pokrytí a testování kódu v editoru kódu sady Visual Studio.

## <a name="intellitest"></a>IntelliTest

IntelliTest automaticky vygeneruje testování částí a testovací data pro spravovaný kód. IntelliTest zlepšuje pokrytí a výrazně snižuje úsilí nezbytné k vytváření a údržbě testů jednotek pro nový nebo existující kód.

![IntelliTest v akci](media/devtest-intellitest.png)

* [Generování testů částí pro kód pomocí funkce IntelliTest](generate-unit-tests-for-your-code-with-intellitest.md)
* [IntelliTest – jeden test pro vládne všem.](https://devblogs.microsoft.com/devops/intellitest-one-test-to-rule-them-all/)
* [Referenční příručka funkce IntelliTest](intellitest-manual/index.md)

## <a name="code-coverage"></a>Pokrytí kódu

[Pokrytí kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md) Určuje, jaká část projektového kódu je skutečně testován kódovanými testy, jako je například testování částí. Pro efektivní ochranu před chybami, testy by měly vykonávat nebo "zahrnují" velká část kódu.

Analýza pokrytí kódu lze použít pro spravovaný i nespravovaný (nativní) kód.

Pokrytí kódu je jedna z možností při spouštění testovacích metod pomocí Průzkumníku testů. Tabulka výsledků zobrazuje procentuální podíl kódu, který byl spuštěn v každém sestavení, třídě a metodě. Editor zdrojového kódu navíc ukazuje samotný kód, který byl testován.

* [Použití pokrytí kódu k určení, kolik kódu je právě testováno.](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Testování částí, pokrytí kódu a analýza duplicit pomocí sady Visual Studio (prostředí) v kódu](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [Přizpůsobení analýzy pokrytí kódu](customizing-code-coverage-analysis.md)

## <a name="microsoft-fakes"></a>Microsoft Fakes

[Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md) může pomoci izolovat kód nahrazením ostatních částí aplikace pomocí zástupných procedur a překrytí testujete.

## <a name="user-interface-testing-with-coded-ui-and-selenium"></a>Uživatelské rozhraní testování pomocí uživatelského rozhraní a serverem Selenium

Programové testy UI poskytují způsob, jak vytvořit plně automatizované testy pro ověření chování vaší aplikace uživatelského rozhraní a funkcí. Můžete se automatizují toto testování v různých technologií, včetně aplikací pro UWP založené na XAML, prohlížečových aplikací a aplikací pro SharePoint.

Jestli si nejlepší druhu programových testů uživatelského rozhraní nebo obecný webové rozhraní testování s Selenium, Visual Studio poskytuje všechny nástroje, které potřebujete.

![Testování pomocí uživatelského rozhraní programového uživatelského rozhraní](media/devtest-codeduitest.png)

* [Použití automatizace uživatelského rozhraní k testování kódu](use-ui-automation-to-test-your-code.md)
* [Začínáme vytvářet, úpravy a údržba programového testu uživatelského rozhraní](walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
* [Testování aplikací pro UWP pomocí programových testů uživatelského rozhraní](test-uwp-app-with-coded-ui-test.md)
* [Úvod do programové testy UI pomocí sady Visual Studio Enterprise (prostředí)](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20Coded%20UI%20Tests%20with%20Visual%20Studio%20Enterprise%202015.docx)

## <a name="load-testing"></a>Zátěžové testování

[Zátěžové testování](../test/quickstart-create-a-load-test-project.md) simuluje zatížení na serveru aplikace spuštěním testů jednotek a testů výkonu webu.

## <a name="related-scenarios"></a>Související scénáře

* [Průzkumné a ručního testování (Azure testovací plány)](/azure/devops/test/index?view=vsts)
* [Zátěžové testování (Azure testovací plány)](/azure/devops/test/load-test/index?view=vsts)
* [Průběžné testování (Azure testovací plány)](/azure/devops/pipelines/test/getting-started-with-continuous-testing?view=vsts)
* [Nástroje pro analýzu kódu](../code-quality/code-analysis-for-managed-code-overview.md)
