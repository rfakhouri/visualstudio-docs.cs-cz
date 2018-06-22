---
title: Přizpůsobení analýzy pokrytí kódu v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 7b48fc77dd88cf327050c0bf8ba893f8d4a626fa
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303000"
---
# <a name="customize-code-coverage-analysis"></a>Přizpůsobení analýzy pokrytí kódu

Ve výchozím nastavení analyzuje pokrytí kódu všechna sestavení řešení, které jsou načteny během testování částí. Vzhledem k tomu, že funguje dobře ve většině případů doporučujeme použít toto výchozí chování. Další informace najdete v tématu [použít pokrytí kódu k určení, kolik kód je testován](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

Pokud chcete vyloučit testovacího kódu z pokrytí výsledky kódu a obsahovat jenom kód aplikace, přidejte <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> atribut ke třídě testu.

Chcete-li zahrnout sestavení, které nejsou součástí vašeho řešení, získat *PDB* soubory pro tyto sestavení a zkopírujte je do stejné složky jako sestavení *.dll* soubory.

## <a name="run-settings-file"></a>Spusťte soubor nastavení

[Spusťte soubor nastavení](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md) je konfigurační soubor použít nástroje pro testování jednotky. Nastavení pokrytí pokročilé kódu jsou určené v *.runsettings* souboru.

Chcete-li přizpůsobit pokrytí kódu, postupujte takto:

1. Přidáte soubor parametrů běhu k řešení. V **Průzkumníku řešení**, v místní nabídce vašeho řešení, zvolte **přidat** > **nová položka**a vyberte **souboru XML**. Uložte soubor s názvem, jako *CodeCoverage.runsettings*.

1. Přidejte obsah ze souboru příkladu na konci tohoto článku a jak je popsáno v následujících částech jej přizpůsobit svým potřebám.

1. Vyberte soubor parametrů běhu na **testovací** nabídce zvolte **nastavení testu** > **vyberte soubor s nastavením testu**. Zadejte soubor parametrů běhu pro spouštění testů z příkazového řádku nebo v pracovním postupu sestavení, najdete v tématu [konfigurace testů jednotek pomocí *.runsettings* soubor](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md#specify-a-run-settings-file).

   Když vyberete **analýza pokrytí kódu**, informace o konfiguraci je čtení ze souboru parametrů běhu.

   > [!TIP]
   > Předchozí výsledky pokrytí kódu a kódu barevné zvýrazňování nejsou skryté automaticky při spuštění testů nebo aktualizaci vašeho kódu.

Vlastní nastavení vypnutí a zapnutí, zrušte výběr nebo vyberte soubor v **Test** > **nastavení testu** nabídky.

![Testování nabídky nastavení se soubor s vlastním nastavením](../test/media/codecoverage-settingsfile.png)

### <a name="specify-symbol-search-paths"></a>Zadejte cesty pro hledání symbolů

Pokrytí kódu vyžaduje soubory symbolů (*PDB* soubory) pro sestavení. Pro sestavení vytvořené řešení jsou soubory symbolů obvykle koexistuje binární soubory a pokrytí kódu funguje automaticky. Ale v některých případech můžete chtít zahrnout odkazovaná sestavení do analýzy pokrytí kódu. V takových případech *PDB* soubory nemusí být přiléhající k binární soubory, ale můžete zadat cestu vyhledávání symbolů v *.runsettings* souboru.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!NOTE]
> Symbol řešení může trvat čas, zejména v případě, že mnoho sestavení pomocí umístění vzdáleného souboru. Zvažte proto kopírování *PDB* soubory do stejného umístění, místní jako binárního souboru (*.dll* a *.exe*) soubory.

### <a name="exclude-and-include"></a>Vyloučení nebo zahrnutí

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

Pokud **zahrnout** je prázdný, pak zpracování pokrytí kódu zahrnuje všechny sestavení, které jsou načtené a pro které *PDB* soubory jsou umístěny. Pokrytí kódu neobsahuje položky, které odpovídají klauzuli v **vyloučit** seznamu.

**Zahrnout** se zpracují dříve, než **vyloučit**.

### <a name="regular-expressions"></a>Regulární výrazy

Pomocí regulárních výrazů můžete zahrnout a vyloučit uzly. Další informace najdete v tématu [použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md). Regulární výrazy nejsou stejná jako zástupné znaky. Zejména:

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
> Pokud dojde k chybě v regulárním výrazu, jako je například neuvozené nebo neodpovídající závorky, analýzy pokrytí kódu se nespustí.

### <a name="other-ways-to-include-or-exclude-elements"></a>Další způsoby zahrnutí nebo vyloučení prvků

- **ModulePath** -odpovídá sestavení určeného cesta k souboru sestavení.

- **NázevSpolečnosti** -odpovídá sestavení pomocí **společnosti** atribut.

- **PublicKeyToken** -odpovídá podepsaný token veřejného klíče sestavení.

- **Zdroj** -odpovídá elementy název cesty zdrojového souboru, ve kterém jsou definovány.

- **Atribut** -odpovídá elementy, na které je připojen konkrétní atribut. Zadejte úplný název atributu a zahrnovat "Atribut" na konci názvu.

- **Funkce** -odpovídá procedury, funkce nebo metody ve plně kvalifikovaný název. Tak, aby odpovídaly názvu funkce, musí odpovídat regulárnímu výrazu plně kvalifikovaný název funkce, včetně oboru názvů, název třídy, název metody a seznam parametrů. Příklad:

   ```csharp
   Fabrikam.Math.LocalMath.SquareRoot(double);
   ```

   ```cpp
   Fabrikam::Math::LocalMath::SquareRoot(double)
   ```

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

## <a name="sample-runsettings-file"></a>Ukázkový soubor s příponou .runsettings

Zkopírujte tento kód a upravit podle svých potřeb.

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

## <a name="see-also"></a>Viz také:

- [Konfigurace testů jednotek pomocí souboru parametrů běhu](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)
- [Použití pokrytí kódu k určení, kolik kód je testována.](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [Testování částí kódu](../test/unit-test-your-code.md)