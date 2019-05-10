---
title: Testování částí
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5682d752ba2c1430d8ab708e3dadda754a1ba757
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461383"
---
# <a name="unit-test-your-code"></a>Testování částí kódu

Testování částí poskytuje vývojářům a testerům rychlý způsob vyhledávání logických chyb v rámci metod tříd v projektech C#, Visual Basic a C++.

Nástroje testování částí zahrnují:

* **Průzkumník testů**&mdash;spouštění testů jednotek a analyzovat jejich výsledky v **Průzkumník testů**. Můžete použít libovolné rozhraní testování částí, včetně rozhraní třetích stran, které má adaptér pro **Průzkumníka testů**.

* **Rámce jednotkových testů společnosti Microsoft pro spravovaný kód**&mdash;rozhraní testování částí Microsoft pro spravovaný kód se instaluje se sadou Visual Studio a poskytuje rozhraní pro testování kódu rozhraní .NET.

* **Rámce jednotkových testů společnosti Microsoft pro jazyk C++**&mdash;Microsoft pro testování částí C++ je nainstalován jako součást **vývoj desktopových aplikací pomocí C++** pracovního vytížení. Poskytuje rozhraní pro testování nativního kódu. Jsou také zahrnuté CTest, Google Test a Boost.Test rozhraní a adaptéry třetích stran jsou k dispozici pro rozhraní pro další testování. Další informace najdete v tématu [zápis testů jednotek pro C/C++](../test/writing-unit-tests-for-c-cpp.md).

* **Nástroje pokrytí kódu**&mdash;můžete určit množství kódu produktu, testování částí kontroluje jedním příkazem v Průzkumníku testů.

* **Izolační rozhraní Microsoft Fakes**&mdash;izolačního můžete vytvořit napodobeniny Microsoft zástupné třídy a metody pro produkční a systémový kód, které vytváří závislosti v kódu v rámci testu. Implementací napodobenin delegátů pro funkci je možné kontrolovat chování a výstup závislého objektu.

Můžete také použít [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md) prozkoumat kód .NET a vygenerovat testovací data a sady testování částí. Pro každý příkaz v kódu se generuje zkušební vstup, který tento příkaz spustí. Pro každou podmíněnou větev v kódu se provede Případová analýza.

## <a name="key-tasks"></a>Klíčové úkoly

Abychom vám pomohli s principy a vytváření testů jednotek pomocí následujících článků:

|Úkoly|Související témata|
|-|-----------------------|
|**Rychlé starty a kurzy:** Další informace o testování v sadě Visual Studio z příkladů kódů.|- [Návod: Vytváření a spouštění testů jednotek pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />- [Rychlý start: Vývoj řízený testováním pomocí Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)<br />- [Jak: Přidání jednotkových testů do C++ aplikace](../test/how-to-use-microsoft-test-framework-for-cpp.md)|
|**Testování částí pomocí Průzkumníka testů:** Zjistěte, jak může Průzkumník testů pomoci vytváření produktivnějších a efektivnějších testů jednotek.|- [Základní informace o testování částí](../test/unit-test-basics.md)<br />- [Vytvořte projekt testu jednotek](../test/create-a-unit-test-project.md)<br />- [Spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)<br />- [Nainstalujte rozhraní pro testování jednotky třetí strany](../test/install-third-party-unit-test-frameworks.md)|
|**Testování částí C++ kódu**|- [Zápis testů jednotek pro C/C++](../test/writing-unit-tests-for-c-cpp.md)|
|**Izolující testování částí**|- [Izolace testovaného kódu pomocí Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md)|
|**Použití pokrytí kódu pro identifikaci, jaká část projektového kódu je testována:** Další informace o funkcích pokrytí kódu testovacích nástrojů sady Visual Studio.|- [Použití pokrytí kódu k určení, kolik kódu je právě testováno.](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|
|**Provedení zátěžové a výkonnostní analýzy použitím zátěžových testů:** Zjistěte, jak vytvořit zátěžové testy pro lepší izolaci výkonnostních a zátěžových problémů aplikace.|- [Rychlý start: Vytvoření projektu zátěžového testu](../test/quickstart-create-a-load-test-project.md)<br />- [Zátěžové testování (Azure testovací plány a sady TFS)](/azure/devops/test/load-test/index?view=vsts)|
|**Nastavení brány kvality:** Zjistěte, jak vytvořit brány kvality k vynucení spuštění testů předtím, než je kód se změnami nebo sloučit.|- [Zásady vrácení se změnami (TFVC úložiště Azure)](/azure/devops/repos/tfvc/add-check-policies?view=vsts)|
|**Nastavení možností testování:** Zjistěte, jak nakonfigurovat možnosti testování, například ukládat výsledky testů.|[Konfigurace testů částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|

## <a name="api-reference-documentation"></a>Referenční dokumentace rozhraní API

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> Popisuje obor názvů UnitTesting, který poskytuje atributy, výjimky, kontrolní výrazy a další třídy této podporují testování částí.
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web> Popisuje obor názvů UnitTesting.Web, který rozšiřuje obor názvů UnitTesting poskytováním podpory pro ASP.NET a webové testy služby.

## <a name="see-also"></a>Viz také:

- [Zlepšení kvality kódu](../test/improve-code-quality.md)
