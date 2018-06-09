---
title: V sadě Visual Studio testování částí
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 487c5b4c730a4b49188857c2681aae6ff87a61e5
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237328"
---
# <a name="unit-test-your-code"></a>Testování částí kódu

Testování částí vývojáři a testerům, sada poskytují rychlý způsob, jak hledat logické chyby v metody třídy v projektu C#, Visual Basic a C++.

Nástroje testování částí zahrnují:

* **Testování Explorer**&mdash;můžete spustit testy jednotek a zobrazte jejich výsledky v **Průzkumníka testů**. Můžete použít libovolnou architekturu test jednotky, včetně rozhraní třetích stran, který má adaptér pro **testování Explorer**.

* **Částí Microsoft unit test framework pro spravovaný kód**&mdash;Microsoft částí unit test framework pro spravovaný kód je nainstalován pomocí sady Visual Studio a poskytuje rozhraní pro kód .NET pro testování.

* **Částí Microsoft unit test framework pro C++**&mdash;Microsoft částí unit test framework pro C++ je nainstalován jako součást **vývoj aplikací s jazykem C++** zatížení. Poskytuje rozhraní pro testování nativního kódu. Google Test, Boost.Test a CTest architektury jsou také zahrnuté a třetích stran adaptéry jsou k dispozici pro další test rozhraní. Další informace najdete v tématu [zápis testování částí pro C/C++](../test/writing-unit-tests-for-c-cpp.md).

* **Nástroje pro pokrytí kódu**&mdash;můžete určit množství paměti, že vaše jednotka testů cvičení z jednoho příkazu v Průzkumníka testů kód produktu.

* **Microsoft Fakes izolace rámec**&mdash;izolace rámec můžete vytvořit Fakes Microsoft nahradit třídy a metody pro kód produkční a systému, které vytvářejí závislosti v testovaného kódu. Implementací napodobenin delegátů pro funkci je možné kontrolovat chování a výstup závislého objektu.

Můžete také použít [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md) prozkoumat ke generování testovacích datech a sada testů částí kódu .NET. Pro každý příkaz v kódu, je generována testovací vstup, spustí tento příkaz. Case analýzy se provádí pro každou podmíněného větve v kódu.

## <a name="key-tasks"></a>Klíčové úkoly

V následujících tématech naleznete informace týkající se vytváření testování částí a sloužící k jeho lepšímu pochopení:

|Úlohy|Související témata|
|-----------|-----------------------|
|**Rychlé zahájení práce a návody:** používat další jednotky testování v sadě Visual Studio z příklady kódu v následujících tématech.|-   [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [Rychlý úvod: Testy řízený vývoj pomocí Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [Přidání testů částí do stávajících aplikací C++](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|
|**Testování částí pomocí Průzkumníka testů:** zjistěte, jak můžete Průzkumníka testů pomocí vytvoření produktivní a efektivní testování částí.|-   [Testování částí](../test/unit-test-basics.md)<br />-   [Vytvoření projektu testování částí](../test/create-a-unit-test-project.md)<br />-   [Spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)<br />-   [Instalace systémů testů jednotek třetích stran](../test/install-third-party-unit-test-frameworks.md)|
|**Testování částí spravovaného kódu:**|-   [Zápis testů částí pro rozhraní .NET Framework s částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|
|**C++ – kód testování částí**|-   [Zápis testů částí pro C/C++ s Microsoft Unit Testing Framework pro C++](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|
|**Uzavírací testování částí**|-   [Izolace testovaného kódu pomocí zástupného rozhraní Microsoft](../test/isolating-code-under-test-with-microsoft-fakes.md)|
|**Použijte pokrytí kódu k určení, jaké části kódu vašeho projektu je testován:** Další informace o funkci pokrytí kódu testovací nástroje sady Visual Studio.|-   [Použití pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|
|**Provést přízvuk a analýza výkonu pomocí zátěžových testů:** můžete vytvořit zátěžový test a přidejte testů jednotek do ní ke zjištění výkonu a vystavila zátěži problémy ve vaší aplikaci.|-   [Spouštění testování (služby VSTS a sady TFS)](/vsts/load-test/)|
|**Nastavení brány kvality:** vytvořením brány kvality vynutit spuštění testů, než se změnami kódu, abyste zajistili kvality kódu.|-   [Vrácení se změnami zásad (VSTS)](/vsts/tfvc/add-check-policies)|
|**Nastavení možností otestování:** například můžete zadat, kde jsou uložené výsledky testů.|[Konfigurace testů částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|

## <a name="api-reference-documentation"></a>Referenční dokumentace rozhraní API

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> Popisuje UnitTesting názvů, který poskytuje atributy, výjimky, vyhodnotí a jiné třídy testování částí tuto podporu.
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web> Popisuje UnitTesting.Web názvů, který rozšiřuje obor názvů UnitTesting tím, že poskytuje podporu pro ASP.NET a webové testy služby.

## <a name="see-also"></a>Viz také:

- [Zlepšení kvality kódu](../test/improve-code-quality.md)
