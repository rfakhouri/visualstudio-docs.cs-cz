---
title: Začínáme s testováním částí
ms.date: 04/01/2019
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit test plans
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a01f08d430e9812283c3f5179e08d20f98a687a4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60072264"
---
# <a name="get-started-with-unit-testing"></a>Začínáme s testováním částí

Visual Studio používejte k definování a spouštění testů jednotek Údržba kódu stavu, ujistěte se pokrytí kódu a najít chyby a závad, než se vaši zákazníci. Spuštění testování částí často a ujistěte se, že váš kód funguje správně.

## <a name="create-unit-tests"></a>Vytvořit testy jednotek

Tato část popisuje jak vytvořit projekt testování částí na vysoké úrovni.

1. Otevřete projekt, který chcete testovat v sadě Visual Studio.

   Pro účely demonstrace testu jednotek příklad v tomto článku testuje Jednoduchý projekt "Hello World". Ukázkový kód pro takový projekt vypadá takto:

   ```csharp
   public class Program
   {
       public static void Main()
       {
           Console.WriteLine("Hello World!");
       }
   }
   ```

1. V **Průzkumníka řešení**, vyberte uzel řešení. Potom v horní nabídce vyberte **souboru** > **přidat** > **nový projekt**.

1. V dialogovém okně Nový projekt najdete testování částí šablona projektu pro testovací rozhraní, které chcete použít a vyberte ji.

   ::: moniker range=">=vs-2019"

   ![Šablona projektu testů jednotek v aplikaci Visual Studio 2019](media/vs-2019/add-new-test-project.png)

   Klikněte na tlačítko **Další**, zvolte název pro testovací projekt a potom klikněte na tlačítko **vytvořit**.

   ::: moniker-end

   ::: moniker range="vs-2017"

   ![Šablona projektu testů jednotek v aplikaci Visual Studio 2019](media/mstest-test-project-template.png)

   Zvolte název pro testovací projekt a potom klikněte na tlačítko **OK**.

   ::: moniker-end

   Projekt je přidán do řešení.

   ![Projekt testu jednotek v Průzkumníku řešení](media/vs-2019/solution-explorer.png)

1. V projektu testování částí přidejte odkaz na projekt, kterou potřebujete otestovat kliknutím pravým tlačítkem na **odkazy** nebo **závislosti** a následným výběrem možnosti **přidat odkaz**.

1. Vyberte projekt, který obsahuje kód, který budete testovat a klikněte na tlačítko **OK**.

   ![Přidat odkaz na projekt v sadě Visual Studio](media/vs-2019/reference-manager.png)

1. Přidejte kód do metody testu jednotek.

   ![Přidejte kód pro metodu testu jednotek v sadě Visual Studio](media/vs-2019/unit-test-method.png)

> [!TIP]
> Detailní postup vytváření testů jednotek, najdete v části [vytvoření a spuštění jednotky testů pro spravovaný kód](walkthrough-creating-and-running-unit-tests-for-managed-code.md).

## <a name="run-unit-tests"></a>Spouštění testů jednotek

1. Otevřít [Průzkumník testů](../test/run-unit-tests-with-test-explorer.md) výběrem **testovací** > **Windows** > **Průzkumník testů** v horní nabídce.

1. Kliknutím na spustit testování částí **spustit všechny**.

   ![Spouštění testování částí v Průzkumníku testů](media/vs-2019/test-explorer-run-all.png)

   Po dokončení testů, zelená značka zaškrtnutí označuje, že test proběhl úspěšně. Ikona s černým symbolem "x" označuje, že se nezdařil test.

   ![Zkontrolujte výsledky testování částí v Průzkumníku testů](media/vs-2019/unit-test-passed.png)

> [!TIP]
> Můžete použít [Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md) ke spuštění testů jednotek z integrované testovací rozhraní (MSTest) nebo z jiného rozhraní testování. Můžete seskupit testy do kategorií, filtrovat seznam testů a vytvořte, uložte a spusťte seznamy stop testů. Můžete také ladit testy a analyzovat pokrytí testu výkonu a kódu.

## <a name="view-live-unit-test-results"></a>Zobrazení výsledků testu jednotek

Pokud používáte MSTest, xUnit a NUnit testovací rozhraní v sadě Visual Studio 2017 nebo později, zobrazí se živé výsledků testování částí.

> [!NOTE]
> Živé testování částí je k dispozici pouze v edici Enterprise.

1. Zapnout z testování jednotek **testovací** nabídek výběrem **testovací** > **Live Unit Testing** > **Start**.

   ::: moniker range="vs-2017"

   ![Zapnout živé testování částí](media/live-test-results-start.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Spustit live unit testing v aplikaci Visual Studio 2019](media/vs-2019/start-live-unit-testing.png)

   ::: moniker-end

1. Zobrazte výsledky testů v rámci okna editoru kódu během psaní a úpravy kódu.

   ![Zobrazit výsledky testů](media/vs-2019/live-unit-testing-results.png)

1. Klikněte na tlačítko na ukazatel výsledku testu pro zobrazení dalších informací, jako jsou názvy testů, které se týkají této metodě.

   ![Vyberte test výsledek ukazatelů](media/vs-2019/live-unit-testing-details.png)

Další informace o živé testování částí v tématu [živé testování částí](../test/live-unit-testing-intro.md).

## <a name="generate-unit-tests-with-intellitest"></a>Generování testů jednotek pomocí funkce IntelliTest

Při spuštění IntelliTest uvidíte, jaké testy se nedaří a přidejte všechny nezbytné kód a opravte je. Můžete vybrat, které z vygenerované testy k uložení do testovacího projektu poskytnout sadu regrese. Po provedení změny kódu, znovu spusťte IntelliTest pro synchronizaci vygenerované testy se změnami kódu. Další informace o postupu [generování testů jednotek pro kód pomocí funkce IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).

> [!TIP]
> IntelliTest je dostupná pouze pro spravovaný kód, který cílí na .NET Framework.

![Generování testů jednotek pomocí funkce IntelliTest](media/intellitest.png)

## <a name="analyze-code-coverage"></a>Analýza pokrytí kódu

Funkci pokrytí kódu sady Visual Studio lze použít ke zjištění toho, jaký podíl kódu projektu je skutečně testován kódovanými testy, jako jsou například jednotkové testy. Pro efektivní ochranu před chybami, vaše testy měly využít velká část kódu. Další informace o postupu [použití pokrytí kódu k určení, kolik kódu je právě testováno](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

## <a name="use-a-third-party-test-framework"></a>Použití rozhraní testování třetích stran

Můžete spustit testy jednotek v sadě Visual Studio s použitím rozhraní testování třetích stran, jako jsou Boost, Google a NUnit. Použití **Správce balíčků NuGet** se nainstalovat balíček NuGet pro rozhraní dle vlastního výběru. Nebo, xUnit a NUnit rozhraních pro testování, Visual Studio obsahuje předem nakonfigurované testovací šablony projektů, které obsahují potřebné balíčky NuGet.

Chcete-li vytvořit jednotkové testy používající [NUnit](https://nunit.org/):

1. Otevřete řešení, která obsahuje kód, který chcete testovat.

2. Klikněte pravým tlačítkem na řešení v **Průzkumníka řešení** a zvolte **přidat** > **nový projekt**.

3. Vyberte **NUnit testovací projekt** šablony projektu.

   ::: moniker range=">=vs-2019"

   ![Šablona projektu test NUnit v Visual Studio 2019](media/vs-2019/nunit-test-project-template.png)

   Klikněte na tlačítko **Další**, pojmenujte projekt a potom klikněte na tlačítko **vytvořit**.

   ::: moniker-end

   ::: moniker range="vs-2017"

   Pojmenujte projekt a potom klikněte na tlačítko **OK** k jeho vytvoření.

   ::: moniker-end

   Šablona projektu obsahuje odkazy na NuGet NUnit a NUnit3TestAdapter.

   ![NUnit NuGet závislosti v Průzkumníku řešení](media/vs-2019/nunit-nuget-dependencies.png)

4. Z testovacího projektu přidejte odkaz na projekt, který obsahuje kód, který chcete testovat.

5. Přidejte kód pro testovací metodu.

   ![Přidejte kód do souboru kódu jednotkového testu](media/vs-2019/unit-test-method.png)

6. Spuštění testu z **Průzkumníka testů** nebo tak, že kliknete pravým tlačítkem na testovací kód a zvolíte **spuštění testů**.

## <a name="see-also"></a>Viz také:

* [Návod: Vytváření a spouštění testů jednotek pro spravovaný kód](walkthrough-creating-and-running-unit-tests-for-managed-code.md)
* [Vytvoření příkazu pro testování částí](create-unit-tests-menu.md)
* [Generování testů s Intellitestem](generate-unit-tests-for-your-code-with-intellitest.md)
* [Spouštění testů pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md)
* [Analýza pokrytí kódu](using-code-coverage-to-determine-how-much-code-is-being-tested.md)