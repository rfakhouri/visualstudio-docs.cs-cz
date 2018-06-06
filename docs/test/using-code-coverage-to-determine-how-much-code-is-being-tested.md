---
title: Pokrytí kódu v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- code coverage
dev_langs:
- CSharp
- VB
- CPP
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d27bc7fe308d7fc268291f58c64f902ff021dbd1
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752089"
---
# <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Použití pokrytí kódu k určení, kolik kódu se testuje

Funkci pokrytí kódu sady Visual Studio lze použít ke zjištění toho, jaký podíl kódu projektu je skutečně testován kódovanými testy, jako jsou například jednotkové testy. Pro efektivní ochranu před chybami je vhodné testovat, neboli „pokrýt“, velkou část kódu projektu.

Analýza pokrytí kódu může být použita jak pro spravovaný (CLI), tak pro nespravovaný (nativní) kód.

Pokrytí kódu je jedna z možností při spouštění testovacích metod pomocí Průzkumníku testů. Tabulka výsledků zobrazuje procentuální podíl kódu, který byl spuštěn v každém sestavení, třídě a metodě. Editor zdrojového kódu navíc ukazuje samotný kód, který byl testován.

![Výsledky pokrytí kódu pomocí barevné zvýrazňování](../test/media/codecoverage1.png)

 **Požadavky**

-   Visual Studio Enterprise

## <a name="to-analyze-code-coverage-on-unit-tests-in-test-explorer"></a>Analýza pokrytí kódu jednotkovými testy v Průzkumníku testů

1.  Na **testovací** nabídky, zvolte **analýza pokrytí kódu**.

2.  Zobrazit linky, které byla spuštěna, vyberte ![zobrazit barvy v ikonu pokrytí kódu](../test/media/codecoverage-showcoloringicon.png)**zobrazit kód pokrytí barvy v**.

     Chcete-li změnit barvy nebo použít tučné řez, zvolte **nástroje** > **možnosti** > **prostředí** > **písem a Barvy** > **zobrazit nastavení pro: textový Editor**. V části **zobrazení položek**, upravte pokrytí položky.

3.  Pokud výsledky zobrazují nízké pokrytí, prozkoumejte, které části kódu nejsou testovány, a vytvořte pro ně další testy. Vývojové týmy obvykle usilují o 80% pokrytí kódu. V některých situacích je přijatelné i nižší pokrytí. Nižší pokrytí je například přijatelné tehdy, pokud je část kódu generována ze standardní šablony.

> [!TIP]
> - Ujistěte se, že tento optimalizace kompilátoru je vypnutý.
> - Pokud pracujete s nespravovaným kódem (nativní), použijte sestavení ladicí verze
> - Ujistěte se, že jste pro každé sestavení generují soubory PDB (symbol).

Pokud neobdržíte očekáváte, že výsledky, najdete v části [řešení potíží s pokrytí kódu](../test/troubleshooting-code-coverage.md). . Nezapomeňte spustit pokrytí kódu po aktualizaci vašeho kódu. Výsledky pokrytí kódu a barevné zvýraznění kódu nejsou po změně kódu nebo při spuštění testů automaticky aktualizovány.

## <a name="report-in-blocks-or-lines"></a>Sestavy v blocích nebo řádky

Pokrytí kódu se počítá *bloky*. Blok je část kódu s právě jedním vstupním a výstupním bodem.  Pokud řízení toku programu prochází blok během spuštění testu, tomto bloku se počítá jako zahrnutý. Počet průchodů blokem nemá na výsledek žádný vliv.

Můžete taky nechat výsledky zobrazí z hlediska řádky výběrem **přidat nebo odebrat sloupce** v záhlaví tabulky. Pokud testovací běh otestoval všechny bloky na jednom řádku kódu, započítá se tento řádek jako úplný řádek. Když řádek obsahuje jak otestované, tak i neotestované bloky, pak se započítá jako částečný řádek.

Někteří uživatelé dávají přednost určování pokrytí podle počtu řádků, protože jeho procenta lépe odpovídají velikosti fragmentů, které jsou vidět ve zdrojovém kódu. Dlouhý blok výpočtu by byl započítán jako jeden blok i v případě, že zabírá mnoho řádků.

## <a name="manage-code-coverage-results"></a>Správa výsledků pokrytí kódu

Okno Výsledky pokrytí kódu obvykle zobrazuje výsledek posledního běhu. Výsledky se budou lišit, pokud dojde ke změně zkušebních dat nebo jsou pokaždé spuštěny jen některé testy.

Okno pokrytí kódu lze také použít k zobrazení předchozích výsledků nebo výsledků získaných na jiných počítačích.

Je také možné sloučit výsledky několika běhů, pokud například používají jiná testovací data.

-   **Chcete-li zobrazit předchozí sadu výsledků**, vyberte z rozevírací nabídky. Nabídka obsahuje dočasný seznam, který je po otevření nového řešení vyprázdněn.

-   **Chcete-li zobrazit výsledky z předchozí relace,**, zvolte **Import výsledků pokrytí kódu**, přejděte do složky TestResults ve vašem řešení a importovat soubor .coverage.

    Vybarvení pokrytí může být nesprávné v případě, že byl zdrojový kód změněn od chvíle vygenerování souboru s příponou .coverage.

-   **Aby byl čitelnější jako text výsledky**, zvolte **exportovat výsledky pokrytí kódu**. Tím se vytvoří soubor s příponou .coveragexml, který je možné zpracovat v jiných nástrojích nebo jednoduše odeslat e-mailem.

-   **Odeslat výsledky někomu jinému**, odeslání .coverage soubor nebo soubor exportovaný .coveragexml. Tento soubor je pak možné importovat. Pokud se navíc shodují verze zdrojového kódu, je možné zobrazit i vybarvení pokrytí.

## <a name="merge-results-from-different-runs"></a>Sloučení výsledky z různých běží

V některých situacích se na základě testovacích dat použijí různé bloky kódu. Může být tedy nutné sloučit výsledky různých testovacích běhů.

 Například při spuštění testu se vstupem „2“ je zjištěno 50% pokrytí určité funkce. Při druhém spuštění testu se vstupem „-2“ se v okně pokrytí zobrazí pokrytí zbylých 50 % funkce. Po sloučení výsledků těchto dvou testovacích běhů ukáže sestava i vybarvení 100% pokrytí funkce.

 Použití ![ikony pro tlačítko sloučení v okně pokrytí kódu](../test/media/codecoverage-mergeicon.png)**sloučení výsledky pokrytí kódu** k tomu. Ke sloučení je možné použít libovolnou kombinaci předešlých běhů nebo importovaných výsledků. Pokud je potřeba sloučit exportované výsledky, je nejprve nutné je importovat.

 Použití **exportovat výsledky pokrytí kódu** uložte výsledky operace sloučení.

### <a name="limitations-in-merging"></a>Omezení při slučování

-   Při sloučení dat pokrytí rozdílných verzí kódu jsou výsledky zobrazeny odděleně, ale nejsou sloučeny. Pro kompletní sloučení výsledků je potřeba použít stejné sestavení kódu pouze s odlišnými testovacími daty.

-   Pokud dojde ke sloučení souboru výsledků, který byl exportován a poté importován, je možné zobrazit výsledky jen podle řádků, nikoli podle bloků. Použití **přidat nebo odebrat sloupce** příkazu zobrazte data řádku.

-   Při sloučení výsledků testů projektu aplikace ASP.NET dojde k zobrazení výsledků samostatných testů, ale ne k jejich sloučení. To platí pouze pro samotné artefakty ASP.NET, výsledky pro jakákoli jiná sestavení budou sloučeny.

## <a name="exclude-elements-from-the-code-coverage-results"></a>Vyloučit elementy z výsledků pokrytí kódu

Je možné vyloučit určité prvky v kódu z výpočtů pokrytí, například proto, že je kód generován z textové šablony. Přidat atribut `System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverage` k některému z následujících elementy kódu: třída, struktura, metoda, vlastnost, Metoda setter vlastnosti nebo getter, událostí. Za povšimnutí stojí, že vyloučení třídy nevylučuje její odvozené třídy.

 Příklad:

```csharp

using System.Diagnostics.CodeAnalysis;
...
public class ExampleClass1
{
    [ExcludeFromCodeCoverage]
    void ExampleMethod() {...}

    [ExcludeFromCodeCoverage] // exclude property
    int ExampleProperty1
    { get {...} set{...}}

    int ExampleProperty2
    {
        get
        {
            ...
        }
        [ExcludeFromCodeCoverage] // exclude setter
        set
        {
            ...
        }
    }

}
[ExcludeFromCodeCoverage]
class ExampleClass2 { ... }

```

```vb
Imports System.Diagnostics.CodeAnalysis

Class ExampleClass1
    <ExcludeFromCodeCoverage()>
    Public Sub ExampleSub1()
        ...
    End Sub

    ' Exclude property
    < ExcludeFromCodeCoverage()>
    Property ExampleProperty1 As Integer
        ...
    End Property

    ' Exclude setter
    Property ExampleProperty2 As Integer
        Get
            ...
        End Get
        <ExcludeFromCodeCoverage()>
        Set(ByVal value As Integer)
            ...
        End Set
    End Property
End Class

<ExcludeFromCodeCoverage()>
Class ExampleClass2
...
End Class
```

```cpp
// A .cpp file compiled as managed (CLI) code.
using namespace System::Diagnostics::CodeAnalysis;
...
public ref class ExampleClass1
{
  public:
    [ExcludeFromCodeCoverage]
    void ExampleFunction1() { ... }

    [ExcludeFromCodeCoverage]
    property int ExampleProperty2 {...}

    property int ExampleProperty2 {
      int get() { ... }
     [ExcludeFromCodeCoverage]
      void set(int value) { ...  }
   }
}

[ExcludeFromCodeCoverage]
public ref class ExampleClass2
{ ... }
```

### <a name="exclude-elements-in-native-c-code"></a>Vyloučit elementy v nativním kódu C++ kódu

Vyloučení nespravovaných (nativních) prvků kódu jazyka C++:

```cpp
#include <CodeCoverage\CodeCoverage.h>
...

// Exclusions must be compiled as unmanaged (native):
#pragma managed(push, off)

// Exclude a particular function:
ExcludeFromCodeCoverage(Exclusion1, L"MyNamespace::MyClass::MyFunction");

// Exclude all the functions in a particular class:
ExcludeFromCodeCoverage(Exclusion2, L"MyNamespace::MyClass2::*");

// Exclude all the functions generated from a particular template:
ExcludeFromCodeCoverage(Exclusion3, L"*::MyFunction<*>");

// Exclude all the code from a particular .cpp file:
ExcludeSourceFromCodeCoverage(Exclusion4, L"*\\unittest1.cpp");

// After setting exclusions, restore the previous managed/unmanaged state:
#pragma managed(pop)
```

Použijte následující makra:

 `ExcludeFromCodeCoverage(` *ExclusionName* `, L"` *%{FunctionName/* `");`

 `ExcludeSourceFromCodeCoverage(` *ExclusionName* `, L"` *cestakezdrojovemusouboru* `");`

-   *ExclusionName* je libovolný jedinečný název.

-   *%{FunctionName/* je funkce plně kvalifikovaný název. Může obsahovat zástupné znaky. Například pokud chcete vyloučit všechny funkce třídy, zápis `MyNamespace::MyClass::*`

-   *Cestakezdrojovemusouboru* je místní nebo cestu UNC k souboru sada. Může obsahovat zástupné znaky. Následující příklad vyloučí všechny soubory v jednom adresáři: `\\MyComputer\Source\UnitTests\*.cpp`

-   `#include <CodeCoverage\CodeCoverage.h>`

-   Umístěte volání maker vyloučení do globálního oboru názvů a nikoli v rámci libovolného oboru názvů nebo třídy.

-   Vyloučení se umisťuje buď do souboru kódu jednotkového testu, nebo do souboru kódu aplikace.

-   Vyloučení musí být zkompilovány jako nespravovaný kód (nativní), a to nastavením možnosti kompilátoru nebo pomocí `#pragma managed(off)`.

> [!NOTE]
> K vyloučení funkce v jazyce C + +/ CLI kódu, použijte atribut `[System::Diagnostics::CodeAnalysis::ExcludeFromCodeCoverage]` funkce. Toto je stejné použití jako v jazyce C#.

### <a name="include-or-exclude-additional-elements"></a>Zahrnout nebo vyloučit další prvky

Analýza pokrytí kódu je provedena pouze u sestavení, která jsou načtena a pro něž je k dispozici soubor s příponou .pdb ve stejném adresáři jako soubor s příponou .dll nebo .exe. Proto je v některých případech možné rozšířit sadu zahrnutých sestavení získáním kopie jejich souborů s příponou .pdb.

Je také možné získat větší kontrolu nad sestaveními a prvky vybranými pro analýzu pokrytí kódu vytvořením souboru .runsettings. Je tak například možné vyloučit určitá sestavení bez nutnosti přidávání atributů jejich třídám. Další informace najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

## <a name="analyze-code-coverage-in-the-build-service"></a>Analýza pokrytí kódu v rámci služby sestavení

Při vrácení kódu se změnami jsou testy spuštěny na serveru sestavení společně se všemi dalšími testy ostatních členů týmu. (Pokud ještě již nastavit tuto možnost, přečtěte si téma [procesu sestavení spustit testy](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) Je užitečné k analýze pokrytí kódu na službu sestavení, protože udávající nejnovější a komplexní přehled o pokrytí v celý projekt. Bude také zahrnovat automatizované systémové testy a jiné programové testy, které nejsou obvykle spustit na počítačích, vývoj.

1. V nástroji Team Explorer otevřete **sestavení**a potom přidat nebo upravit definici buildu.

2. Na **proces** rozbalte **automatizovaných testů**, **Test zdroje**, **spustit nastavení**. Nastavit **typ souboru parametrů běhu** k **Code pokrytí povoleno**.

   Pokud máte více než jednu definici Zdroje testu, opakujte tento krok pro každou z nich.

   ![Nastavení definici sestavení pro pokrytí kódu](../test/media/codecoverage-plaincc.png)

> [!TIP]
> Pokud není k dispozici žádné pole s názvem **typ spuštění nastavení souboru**, změnit **Test Runner** vlastnost. V části **automatizovaných testů**, vyberte **testovací sestavení** a zvolte tlačítko se třemi tečkami **[...]**  na konci řádku. V **spuštění testu, přidat či upravit** dialogovém **Test Runner**, zvolte **Visual Studio Test Runner**.

Když sestavení proběhne, jsou výsledků pokrytí kódu připojeny k testovacímu běhu a zobrazí se v přehledu sestavení.

## <a name="analyze-code-coverage-in-a-command-line"></a>Analýza pokrytí kódu v příkazovém řádku

Pro spuštění testů z příkazového řádku se používá příkaz vstest.console.exe. Pokrytí kódu je možnost vstest.console.exe nástroje.

1.  Spusťte příkazový řádek pro vývojáře v sadě Visual Studio:

    V systému Windows **spustit** nabídce zvolte **Visual Studio 2017** > **příkazový řádek vývojáře pro VS 2017**.

2.  Spusťte následující příkaz:

    `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage`

## <a name="troubleshoot"></a>Řešení potíží

Pokud se nezobrazí výsledky pokrytí kódu, [řešení potíží s pokrytí kódu](../test/troubleshooting-code-coverage.md) tématu vám můžou pomoct.

## <a name="see-also"></a>Viz také:

- [Přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md)
- [Poradce při potížích s pokrytím kódu](../test/troubleshooting-code-coverage.md)
- [Testování částí kódu](../test/unit-test-your-code.md)
