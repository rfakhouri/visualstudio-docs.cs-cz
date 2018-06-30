---
title: Začínáme s jednotkou testování v sadě Visual Studio
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit test plans
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5101040d52527a80c7531d4984ead5cb4061f70f
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117248"
---
# <a name="get-started-with-unit-testing"></a>Začínáme s testování částí

Pomocí sady Visual Studio můžete definovat a spouštění testů jednotek Udržovat kód stavu, zkontrolujte pokrytí kódu a k nalezení chyb a závad před vašich zákazníků.

## <a name="create-unit-tests"></a>Vytvářet testy částí

Vytvářet testy částí a spustit je často a ujistěte se, že váš kód pracuje správně.

1. Vytvoření projektu testování částí.

   ![Přidání projektu testů jednotek do řešení](media/createunittest1.png)

1. Název projektu.

   ![Šablona projektu testů jednotek](media/createunittest2.png)

   Projekt se přidá do vašeho řešení.

   ![Projektu testů jednotek v Průzkumníku řešení](media/createunittest5.png)

1. V projektu testování částí přidáte odkaz na projekt, který chcete testovat.

   ![Přidat odkaz na vaši projektu testování částí](media/createunittest6.png)

1. Vyberte projekt, který obsahuje kód, který budete testovat.

   ![Vyberte odkazu pro přidání](media/createunittest7.png)

1. Vaše testování částí kódu.

   ![Přidání kódu do vaší testování částí](media/createunittest8.png)

Můžete také vytvořit testování částí zástupných procedury metoda s **vytvořit testování částí** [příkaz](create-unit-tests-menu.md).

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>Spouštění testování částí

1. Otevřete Průzkumníka testů.

   ![V nabídce testovací otevřete Průzkumníka testů](media/rununittest1.png)

1. Spouštění testů jednotek.

   ![Spouštění testů jednotek v Průzkumníka testů](media/rununittest2.png)

   Uvidíte, že jednotka testy, které předán nebo selhání v Průzkumníka testů.

   ![Zkontrolujte výsledky testů jednotek v Průzkumníku testování](media/rununittest3.png)

## <a name="view-live-unit-test-results"></a>Zobrazení výsledků testů jednotek za provozu

Pokud používáte Mstestu, xUnit nebo NUnit testování framework Visual Studio 2017 nebo novější, se zobrazí za provozu výsledky testů jednotek.

> [!NOTE]
> Testování částí za provozu je pouze k dispozici v aplikaci Visual Studio 2017 Enterprise Edition.

1. Zapnout testování z částí za provozu **Test** nabídky.

   ![Zapnout za provozu testování částí](media/live-test-results-start.png)

1. Zápis a úpravy kódu zobrazte výsledky testů v okně editoru kódu.

   ![Zobrazit výsledky testů](media/live-test-results-ui.png)

1. Vyberte testovací výsledek indikátory zobrazíte další informace.

   ![Zvolte indikátory výsledků testu](media/live-test-results-details.png)

Další podrobnosti najdete v tématu [za provozu testování částí](../test/live-unit-testing-intro.md).

## <a name="generate-unit-tests-with-intellitest"></a>Generování testů částí s IntelliTest

Při spuštění IntelliTest snadno uvidíte které testy se nedaří a přidejte všechny nezbytné kód je opravit. Můžete vybrat, které generovaného testů uložit do testovacího projektu zajistit sada regrese. Při změně kódu se znovu spustí IntelliTest pro synchronizaci generovaného testy s vašimi změnami kódu. Další informace, jak zjistit, [generování testů částí kódu s IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).

![Generování testů jednotek s IntelliTest](media/intellitest.png)

## <a name="run-unit-tests-with-test-explorer"></a>Spouštění testů jednotek pomocí Průzkumníka testů

Pomocí Průzkumníka testů spouštění testování částí v sadě Visual Studio nebo projektů testování částí třetích stran, seskupení testů do kategorií, filtrování seznamu testů a vytvořit, uložit a spustit seznamy stop testů. Můžete také ladění testy a analyzovat pokrytí test výkonu a kód. Další informace, jak zjistit, [spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md).

![Spouštění testů jednotek pomocí Průzkumníka testů](media/testexplorer.png)

## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Použití pokrytí kódu k určení, kolik kódu se testuje

Funkci pokrytí kódu sady Visual Studio lze použít ke zjištění toho, jaký podíl kódu projektu je skutečně testován kódovanými testy, jako jsou například jednotkové testy. Pro efektivní ochranu před chybami je vhodné testovat, neboli „pokrýt“, velkou část kódu projektu. Další informace, jak zjistit, [použití pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

![Použití pokrytí kódu k určení, kolik kódu se testuje](media/codecoverage.png)

## <a name="use-a-different-unit-test-framework"></a>Použít různých částí unit test framework

Testování částí v sadě Visual Studio můžete spustit pomocí rozhraní test třetích stran například nárůst, Google a nUnit. Používání, že Visual Studio test runner mohli pracovat s dané platformy pro rozhraní modulu plug-in.

Následují postup povolení systémů testování částí třetí:

1. Zvolte **nástroje** > **rozšíření a aktualizace** z řádku nabídek.

1. V **rozšíření a aktualizace** dialogové okno, rozbalte seznam **Online** kategorie a potom **Visual Studio Marketplace**. Pak zvolte **nástroje** > **testování**.

   ![Visual Studio Marketplace](media/extensions-and-updates-testing.png)

1. Vyberte framework nebo adaptér chcete nainstalovat a potom vyberte **Stáhnout**.

1. Vytvoření projektu knihovny tříd a přidejte ji do vašeho řešení.

   ![Název projektu knihovny tříd a přidejte ji](media/create3rdpartyunittest3.png)

1. Instalace modulu plug-in. V **Průzkumníku řešení**, vyberte projektu knihovny tříd a poté zvolte **spravovat balíčky NuGet** z jeho klikněte pravým tlačítkem nebo kontextové nabídky.

   ![Správa balíčků NuGet k instalaci modulu plug-in](media/create3rdpartyunittest3a.png)

   [NuGet](https://www.nuget.org/) je rozšíření sady Visual Studio, který můžete použít k přidání a aktualizace knihovny a nástroje pro projekty.

1. V **Správce balíčků NuGet** vyhledejte a vyberte modul plug-in a potom zvolte **nainstalovat**.

   ![Nainstalujte rozhraní framework vaší strany 3.](media/create3rdpartyunittest4.png)

   Rozhraní framework odkazuje ve vašem projektu.

   ![Referenční dokumentace pro systém testování částí 3. stran se přidá do vašeho řešení](media/create3rdpartyunittest6.png)

1. Z projektu knihovny tříd **odkazy** uzlu, vyberte **přidat odkaz na**.

   ![Přidat odkaz na projekt](media/createunittest6.png)

1. V **správce odkazů** dialogovém okně vyberte projekt, který obsahuje kód, který budete testovat.

   ![Vyberte kód projekt testování](media/createunittest7.png)

1. Vaše testování částí kódu.

   ![Přidání kódu do vaší testování částí](media/create3rdpartyunittest7.png)

## <a name="see-also"></a>Viz také:

* [Vytvoření příkazu pro testování částí](create-unit-tests-menu.md)
* [Generování testů s IntelliTest](generate-unit-tests-for-your-code-with-intellitest.md)
* [Spouštění testů pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md)
* [Určení pokrytí kódu](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Zlepšení kvality kódu](improve-code-quality.md)