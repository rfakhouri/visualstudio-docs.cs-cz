---
title: "Přizpůsobení analýzy pokrytí kódu v sadě Visual Studio | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 4038b5837503910e46cb1d59a54b4a8038d4699c
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="customize-code-coverage-analysis"></a>Přizpůsobení analýzy pokrytí kódu

Ve výchozím nastavení nástroj Visual Studio pokrytí kódu analyzuje všechny sestavení řešení, které jsou načteny během testování částí. Doporučujeme zachovat toto výchozí nastavení, protože ve většině případů funguje dobře. Další informace najdete v tématu [pomocí pokrytí kódu k určení jak mnohem kódu se testuje](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

Před přizpůsobením chování pokrytí kódu je třeba zvážit některé alternativy:

- *Chcete vyloučit testovacího kódu z pokrytí výsledky kódu a obsahovat pouze kódu aplikace.*

     Přidat `ExcludeFromCodeCoverage Attribute` ke třídě testu.

- *Chcete zahrnout sestavení, které nejsou součástí mém řešení.*

     Získejte soubory s příponou .pdb pro tato sestavení a zkopírujte je do stejné složky jako soubory sestavení s příponou .dll.

Chcete-li přizpůsobit chování pokrytí kódu, zkopírujte [ukázku na konci tohoto tématu](#sample) a přidejte ji do řešení, použijte příponu souboru *.runsettings*. Upravit vlastní potřebám a potom na **Test** nabídce zvolte **nastavení testu**, **vyberte nastavení testu** souboru. Zbývající část tohoto článku popisuje tento postup podrobněji.

## <a name="the-run-settings-file"></a>Soubor parametrů běhu

Nastavení pokrytí pokročilé kódu jsou určené v *.runsettings* souboru. Soubor parametrů běhu je konfigurační soubor nástrojích pro testování jednotky. Doporučujeme vám, že zkopírujete [ukázku na konci tohoto tématu](#sample) a upravit ho podle vlastních potřeb.

Chcete-li přizpůsobit pokrytí kódu, přidáte soubor parametrů běhu k řešení:

1. Přidání souboru .xml jako položka řešení s příponou *.runsettings*:

     V Průzkumníku řešení, vyberte v místní nabídce vašeho řešení **přidat** > **nová položka**a vyberte **souboru XML**. Uložte soubor s názvem, jako ukončení *CodeCoverage.runsettings*.

2. Přidejte obsah z příkladu na konci tohoto článku a jak je popsáno v následujících částech jej přizpůsobit svým potřebám.

3. Na **Test** nabídce zvolte **nastavení testu** > **vyberte soubor s nastavením testu** a vyberte soubor.

4. Nyní když spustíte **analýza pokrytí kódu**, soubor parametrů běhu bude kontrolovat své chování. Nezapomeňte, že je nutné znovu spustit pokrytí kódu. Předchozí výsledky pokrytí a barevné zvýrazňování kódu nejsou skryté automaticky při spuštění testů nebo aktualizaci vašeho kódu.

5. Vlastní nastavení vypnutí a zapnutí, zrušte výběr nebo vyberte soubor v **Test** > **nastavení testu** nabídky.

 ![Testování nabídky nastavení se soubor s vlastním nastavením](../test/media/codecoverage-settingsfile.png)

Další aspekty testování částí lze nakonfigurovat ve stejném souboru parametrů běhu. Další informace najdete v tématu [si kód Test jednotky](../test/unit-test-your-code.md).

### <a name="specifying-symbol-search-paths"></a>Určení cest pro hledání symbolů

Pokrytí kódu vyžaduje, aby byly pro sestavení k dispozici symboly (soubory s příponou .pdb). Pro sestavení vytvořené řešení jsou obvykle koexistuje binární soubory soubory symbolů a pokrytí kódu funguje automaticky. Ale v některých případech můžete chtít zahrnout odkazovaná sestavení do analýzy pokrytí kódu. V takových případech se nemusí soubory s příponou .pdb nacházet u binárních souborů, ale můžete zadat cestu pro hledání symbolů v souboru s příponou .runsettings.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!WARNING]
> Symbol řešení může trvat čas, zejména v případě, že mnoho sestavení pomocí umístění vzdáleného souboru. Zvažte proto možnost zkopírování vzdálených souborů s příponou .pdb do stejného umístění jako binární soubory (.dll a .exe).

### <a name="excluding-and-including"></a>Vyloučení a zahrnutí

Vybraná sestavení lze vyloučit z analýzy pokrytí kódu. Příklad:

```xml
<ModulePaths>
  <Exclude>
   <ModulePath>Fabrikam.Math.UnitTest.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Exclude>
</ModulePaths>
```

Nebo naopak můžete vybrat sestavení, která chcete do analýzy zahrnout. Tento přístup má tu nevýhodu, že při přidání více sestavení k řešení je nesmíte zapomenout přidat do seznamu:

```xml
<ModulePaths>
  <Include>
   <ModulePath>Fabrikam.Math.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Include>
</ModulePaths>
```

Pokud `<Include>` je prázdný, pak zpracování pokrytí kódu zahrnuje všechny sestavení, které jsou načteny, a u kterého lze nalézt soubory PDB. Pokrytí kódu neobsahuje položky, které odpovídají klauzuli v `<Exclude>` seznamu.

`Include` se zpracují dříve, než `Exclude`.

### <a name="regular-expressions"></a>Regulární výrazy

Pomocí regulárních výrazů můžete zahrnout a vyloučit uzly. Další informace najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md). Regulární výrazy nejsou stejné jako zástupné znaky. Zejména:

- **. \***  odpovídá řetězci všech znaků

- **\\.** odpovídá tečku ".")

- **\\( \\)** odpovídá závorkách "(")

- **\\\\** odpovídá oddělovač cestu souboru "\\"

- **^** odpovídá začátku řetězce

- **$** odpovídá konci řetězce

Ve shodách se nerozlišují velká a malá písmena.

Příklad:

```xml
<ModulePaths>
  <Include>
    <!-- Include all loaded .dll assemblies (but not .exe assemblies): -->
    <ModulePath>.*\.dll$</ModulePath>
  </Include>
  <Exclude>
    <!-- But exclude some assemblies: -->
    <ModulePath>.*\\Fabrikam\.MyTests1\.dll$</ModulePath>
    <!-- Exclude all file paths that contain "Temp": -->
    <ModulePath>.*Temp.*</ModulePath>
  </Exclude>
</ModulePaths>
```

> [!WARNING]
> Pokud je v regulárním výrazu chyba, jako například neřídící a nesprávně umístěné závorky, analýza pokrytí kódu se nespustí.

### <a name="other-ways-to-include-or-exclude-elements"></a>Další způsoby zahrnutí nebo vyloučení prvků

Najdete v článku [ukázku na konci tohoto tématu](#sample) příklady.

- `ModulePath` -Sestavení určeného cesta k souboru sestavení.

- `CompanyName` -odpovídá sestavení s atributem společnosti.

- `PublicKeyToken` -odpovídá podepsaný token veřejného klíče sestavení. Například tak, aby odpovídaly všechny součásti sady Visual Studio a rozšíření, použijte `<PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>`.

- `Source` -název cesty zdrojového souboru, ve kterém jsou definovány odpovídá elementy.

- `Attribute` -odpovídá elementy, na které je připojen konkrétní atribut. Zadejte úplný název atributu včetně výrazu „Atribut“ na konci názvu.

- `Function` -odpovídá procedury, funkce nebo metody ve plně kvalifikovaný název.

**Odpovídající název funkce**

Regulární výraz musí odpovídat plně kvalifikovaný název funkce, včetně oboru názvů, název třídy, název metody a seznam parametrů. Například

- C# nebo Visual Basic: `Fabrikam.Math.LocalMath.SquareRoot(double)`

- C++:  `Fabrikam::Math::LocalMath::SquareRoot(double)`

```xml
<Functions>
  <Include>
    <!-- Include methods in the Fabrikam namespace: -->
    <Function>^Fabrikam\..*</Function>
    <!-- Include all methods named EqualTo: -->
    <Function>.*\.EqualTo\(.*</Function>
  </Include>
  <Exclude>
    <!-- Exclude methods in a class or namespace named UnitTest: -->
    <Function>.*\.UnitTest\..*</Function>
  </Exclude>
</Functions>
```

## <a name="how-to-specify-run-settings-files-while-running-tests"></a>Určení parametrů běhu souborů při spouštění testů

### <a name="to-customize-run-settings-in-visual-studio-tests"></a>Chcete-li přizpůsobit parametrů běhu v sadě Visual Studio testů

Zvolte **Test** > **nastavení testu** > **vyberte soubor s nastavením testu** a vyberte *.runsettings* soubor. Soubor se zobrazí v nabídce Nastavení testu a můžete jej vybrat nebo zrušit. Po výběru souboru parametrů běhu platí vždy, když používáte **analýza pokrytí kódu**.

### <a name="to-customize-run-settings-in-a-command-line-test"></a>Chcete-li přizpůsobit parametrů běhu v testů z příkazového řádku

Ke spuštění testů z příkazového řádku, použijte *vstest.console.exe*. Soubor nastavení je parametr tohoto nástroje.

1. Spusťte příkazový řádek pro vývojáře v sadě Visual Studio:

    V systému Windows **spustit** nabídce zvolte **Visual Studio 2017** > **příkazový řádek vývojáře pro VS 2017**.

2. Spusťte následující příkaz:

    `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage /Settings:CodeCoverage.runsettings`

### <a name="to-customize-run-settings-in-a-build-definition"></a>Přizpůsobení parametrů spuštění v definici sestavení

Data pokrytí kódu můžete získat ze sestavení týmu.

![Určení runsettings v definici sestavení](../test/media/codecoverage-buildrunsettings.png)

1. Ujistěte se, že vaše nastavení spuštění souboru se změnami.

2. V nástroji Team Explorer otevřete **sestavení**a potom přidat nebo upravit definici buildu.

3. Na **proces** rozbalte **automatizovaných testů** > **Test zdroje** > **spustit nastavení**. Vyberte *.runsettings* souboru.

   > [!TIP]
   > Pokud **testovací sestavení** se zobrazí místo **Test zdroje**, a můžete vybrat pouze *.testsettings* soubory, nastavte **Test Runner** vlastnost následujícím způsobem. V části **automatizovaných testů**, vyberte **testovací sestavení**a potom zvolte **[...]**  na konci řádku. V **spuštění testu, přidat či upravit** dialogové okno, sada **Test Runner** k **Visual Studio Test Runner**.

Výsledky jsou zobrazeny v souhrnné části zprávy o sestavení.

##  <a name="sample"></a> Ukázka souboru .runsettings

Zkopírujte tento kód a upravte jej podle svých potřeb.

(Pro jiné účely souboru parametrů běhu, najdete v části [konfigurace testů jednotek pomocí souboru parametrů běhu](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).)

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- File name extension must be .runsettings -->
<RunSettings>
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">
        <Configuration>
          <CodeCoverage>
<!--
Additional paths to search for .pdb (symbol) files. Symbols must be found for modules to be instrumented.
If .pdb files are in the same folder as the .dll or .exe files, they are automatically found. Otherwise, specify them here.
Note that searching for symbols increases code coverage runtime. So keep this small and local.
-->
<!--
            <SymbolSearchPaths>
                   <Path>C:\Users\User\Documents\Visual Studio 2012\Projects\ProjectX\bin\Debug</Path>
                   <Path>\\mybuildshare\builds\ProjectX</Path>
            </SymbolSearchPaths>
-->

<!--
About include/exclude lists:
Empty "Include" clauses imply all; empty "Exclude" clauses imply none.
Each element in the list is a regular expression (ECMAScript syntax). See http://msdn.microsoft.com/library/2k3te2cs.aspx.
An item must first match at least one entry in the include list to be included.
Included items must then not match any entries in the exclude list to remain included.
-->

            <!-- Match assembly file paths: -->
            <ModulePaths>
              <Include>
                <ModulePath>.*\.dll$</ModulePath>
                <ModulePath>.*\.exe$</ModulePath>
              </Include>
              <Exclude>
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
              </Exclude>
            </ModulePaths>

            <!-- Match fully qualified names of functions: -->
            <!-- (Use "\." to delimit namespaces in C# or Visual Basic, "::" in C++.)  -->
            <Functions>
              <Exclude>
                <Function>^Fabrikam\.UnitTest\..*</Function>
                <Function>^std::.*</Function>
                <Function>^ATL::.*</Function>
                <Function>.*::__GetTestMethodInfo.*</Function>
                <Function>^Microsoft::VisualStudio::CppCodeCoverageFramework::.*</Function>
                <Function>^Microsoft::VisualStudio::CppUnitTestFramework::.*</Function>
              </Exclude>
            </Functions>

            <!-- Match attributes on any code element: -->
            <Attributes>
              <Exclude>
                <!-- Don't forget "Attribute" at the end of the name -->
                <Attribute>^System\.Diagnostics\.DebuggerHiddenAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.DebuggerNonUserCodeAttribute$</Attribute>
                <Attribute>^System\.Runtime\.CompilerServices.CompilerGeneratedAttribute$</Attribute>
                <Attribute>^System\.CodeDom\.Compiler.GeneratedCodeAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.CodeAnalysis.ExcludeFromCodeCoverageAttribute$</Attribute>
              </Exclude>
            </Attributes>

            <!-- Match the path of the source files in which each method is defined: -->
            <Sources>
              <Exclude>
                <Source>.*\\atlmfc\\.*</Source>
                <Source>.*\\vctools\\.*</Source>
                <Source>.*\\public\\sdk\\.*</Source>
                <Source>.*\\microsoft sdks\\.*</Source>
                <Source>.*\\vc\\include\\.*</Source>
              </Exclude>
            </Sources>

            <!-- Match the company name property in the assembly: -->
            <CompanyNames>
              <Exclude>
                <CompanyName>.*microsoft.*</CompanyName>
              </Exclude>
            </CompanyNames>

            <!-- Match the public key token of a signed assembly: -->
            <PublicKeyTokens>
              <!-- Exclude Visual Studio extensions: -->
              <Exclude>
                <PublicKeyToken>^B77A5C561934E089$</PublicKeyToken>
                <PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>
                <PublicKeyToken>^31BF3856AD364E35$</PublicKeyToken>
                <PublicKeyToken>^89845DCD8080CC91$</PublicKeyToken>
                <PublicKeyToken>^71E9BCE111E9429C$</PublicKeyToken>
                <PublicKeyToken>^8F50407C4E9E73B6$</PublicKeyToken>
                <PublicKeyToken>^E361AF139669C375$</PublicKeyToken>
              </Exclude>
            </PublicKeyTokens>

            <!-- We recommend you do not change the following values: -->
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
            <CollectFromChildProcesses>True</CollectFromChildProcesses>
            <CollectAspDotNet>False</CollectAspDotNet>

          </CodeCoverage>
        </Configuration>
      </DataCollector>
    </DataCollectors>
  </DataCollectionRunSettings>
</RunSettings>
```

## <a name="see-also"></a>Viz také

- [Použití pokrytí kódu k určení rozsahu testovaného kódu](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [Testování částí kódu](../test/unit-test-your-code.md)