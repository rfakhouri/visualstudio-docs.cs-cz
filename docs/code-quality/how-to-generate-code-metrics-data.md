---
title: Generovat metriky kódu z rozhraní IDE nebo příkazového řádku
ms.date: 11/02/2018
ms.topic: conceptual
helpviewer_keywords:
- code metrics data
- code metrics results
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8e43273823c3baca77bfa50206c9b2186118cca8
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007355"
---
# <a name="how-to-generate-code-metrics-data"></a>Postupy: Vygenerování dat metrik kódu

Můžete generování výsledků metrik kódu pro jeden nebo více projektů nebo celého řešení. Metriky kódu jsou k dispozici interaktivní vývojového prostředí (IDE) sady Visual Studio a pro C# a projekty Visual Basic, na příkazovém řádku.

Kromě toho můžete nainstalovat [balíček NuGet](https://dotnet.myget.org/feed/roslyn-analyzers/package/nuget/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.2-beta2-63202-01) , který obsahuje čtyři metriky kódu [analyzátor](roslyn-analyzers-overview.md) pravidla: CA1501 CA1502, CA1505 a CA1506. Tato pravidla jsou ve výchozím nastavení zakázané, ale můžete povolit jim **Průzkumníku řešení** nebo [sada pravidel, která](using-rule-sets-to-group-code-analysis-rules.md) souboru.

## <a name="visual-studio-ide-code-metrics"></a>Visual Studio IDE metriky kódu

Generovat metriky kódu pro jeden nebo více vašich projektů otevřených v integrovaném vývojovém prostředí pomocí **analyzovat** > **vypočítat metriky kódu** nabídky.

### <a name="generate-code-metrics-results-for-an-entire-solution"></a>Generování výsledků metrik kódu pro celé řešení

Výsledky metrik kódu pro celé řešení lze vytvořit v některém z následujících způsobů:

- Na panelu nabídek zvolte **analyzovat** > **vypočítat metriky kódu** > **pro řešení**.

- V **Průzkumníka řešení**, klikněte pravým tlačítkem na řešení a klikněte na tlačítko **vypočítat metriky kódu**.

- V **výsledků metrik kódu** okna, vyberte **vypočítat metriky kódu pro řešení** tlačítko.

Výsledky jsou generovány a **výsledků metrik kódu** se zobrazí okno. Chcete-li zobrazit detaily výsledků, rozbalte stromovou strukturu v **hierarchie** sloupce.

### <a name="generate-code-metrics-results-for-one-or-more-projects"></a>Generování výsledků metrik kódu pro jeden nebo více projektů

1. V **Průzkumníka řešení**, vyberte jeden nebo více projektů.

1. Na panelu nabídek zvolte **analyzovat** > **vypočítat metriky kódu** > **pro vybrané projekty**.

Výsledky jsou generovány a **výsledků metrik kódu** se zobrazí okno. Chcete-li zobrazit detaily výsledků, rozbalte stromovou strukturu v **hierarchie**.

::: moniker range="vs-2017"

> [!NOTE]
> **Vypočítat metriky kódu** příkaz nefunguje pro projekty .NET Core a .NET Standard. Chcete-li vypočítat metriky kódu pro projekt .NET Core nebo .NET Standard, můžete:
>
> - Vypočítat metriky kódu z [příkazového řádku](#command-line-code-metrics) místo
> - upgrade na Visual Studio 2019

::: moniker-end

## <a name="command-line-code-metrics"></a>Metriky kódu příkazového řádku

Můžete vygenerování dat metrik kódu z příkazového řádku pro C# a projekty Visual Basic pro aplikace rozhraní .NET Framework, .NET Core a .NET Standard. Chcete-li spustit kód metriky z příkazového řádku, nainstalovat [balíček Microsoft.CodeAnalysis.Metrics NuGet](#microsoftcodeanalysismetrics-nuget-package) nebo sestavení [Metrics.exe](#metricsexe) spustitelný sami.

### <a name="microsoftcodeanalysismetrics-nuget-package"></a>Balíček Microsoft.CodeAnalysis.Metrics NuGet

Po instalaci je nejjednodušší způsob, jak vygenerování dat metrik kódu z příkazového řádku [Microsoft.CodeAnalysis.Metrics](https://www.nuget.org/packages/Microsoft.CodeAnalysis.Metrics/) balíček NuGet. Po instalaci balíčku, spusťte `msbuild /t:Metrics` z adresáře, který obsahuje váš soubor projektu. Příklad:

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:29:57 PM.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics\Metrics.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:ClassLibrary3.Metrics.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'ClassLibrary3.Metrics.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

Název výstupního souboru můžete přepsat zadáním `/p:MetricsOutputFile=<filename>`. Můžete také získat [starý styl](#previous-versions) data metrik kódu tak, že zadáte `/p:LEGACY_CODE_METRICS_MODE=true`. Příklad:

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics /p:LEGACY_CODE_METRICS_MODE=true /p:MetricsOutputFile="Legacy.xml"
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:31:00 PM.
The "MetricsOutputFile" property is a global property, and cannot be modified.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics.Legacy\Metrics.Legacy.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:Legacy.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'Legacy.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

### <a name="code-metrics-output"></a>Výstup metrik kódu

Generovaný výstup XML má následující formát:

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeMetricsReport Version="1.0">
  <Targets>
    <Target Name="ConsoleApp20.csproj">
      <Assembly Name="ConsoleApp20, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null">
        <Metrics>
          <Metric Name="MaintainabilityIndex" Value="100" />
          <Metric Name="CyclomaticComplexity" Value="1" />
          <Metric Name="ClassCoupling" Value="1" />
          <Metric Name="DepthOfInheritance" Value="1" />
          <Metric Name="LinesOfCode" Value="11" />
        </Metrics>
        <Namespaces>
          <Namespace Name="ConsoleApp20">
            <Metrics>
              <Metric Name="MaintainabilityIndex" Value="100" />
              <Metric Name="CyclomaticComplexity" Value="1" />
              <Metric Name="ClassCoupling" Value="1" />
              <Metric Name="DepthOfInheritance" Value="1" />
              <Metric Name="LinesOfCode" Value="11" />
            </Metrics>
            <Types>
              <NamedType Name="Program">
                <Metrics>
                  <Metric Name="MaintainabilityIndex" Value="100" />
                  <Metric Name="CyclomaticComplexity" Value="1" />
                  <Metric Name="ClassCoupling" Value="1" />
                  <Metric Name="DepthOfInheritance" Value="1" />
                  <Metric Name="LinesOfCode" Value="7" />
                </Metrics>
                <Members>
                  <Method Name="void Program.Main(string[] args)" File="C:\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
                    <Metrics>
                      <Metric Name="MaintainabilityIndex" Value="100" />
                      <Metric Name="CyclomaticComplexity" Value="1" />
                      <Metric Name="ClassCoupling" Value="1" />
                      <Metric Name="LinesOfCode" Value="4" />
                    </Metrics>
                  </Method>
                </Members>
              </NamedType>
            </Types>
          </Namespace>
        </Namespaces>
      </Assembly>
    </Target>
  </Targets>
</CodeMetricsReport>
```

### <a name="metricsexe"></a>Metrics.exe

Pokud nechcete nainstalovat balíček NuGet, můžete vygenerovat a použít *Metrics.exe* přímo spustitelnému souboru. Ke generování *Metrics.exe* spustitelný:

1. Klonování [dotnet /-analyzátory roslyn](https://github.com/dotnet/roslyn-analyzers) úložiště.
2. Otevřete příkazový řádek pro vývojáře pro sadu Visual Studio jako správce.
3. Z kořenové složky **analyzátory roslyn** úložiště, spusťte následující příkaz: `Restore.cmd`
4. Změňte adresář na *src\Tools*.
5. Spusťte následující příkaz k sestavení **Metrics.csproj** projektu:

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   Spustitelný soubor s názvem *Metrics.exe* generován *artifacts\bin* adresáře v kořenovém adresáři úložiště.

#### <a name="metricsexe-usage"></a>Metrics.exe využití

Ke spuštění *Metrics.exe*, zadat projekt nebo řešení a výstup XML souboru jako argumenty. Příklad:

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

#### <a name="legacy-mode"></a>Režim starší verze

Můžete také sestavit *Metrics.exe* v *režim starší verze*. Režim starší verze nástroje generuje hodnoty metrik, které jsou blíž k co [starší verze generovaných nástrojem](#previous-versions). Kromě toho v režimu starší verze *Metrics.exe* generuje metriky kódu pro stejnou sadu metoda typy, které jsou předchozí verze generovaných nástrojem metriky kódu pro. Například pro pole a vlastnosti inicializátory negeneroval dat metrik kódu. Starší režim je užitečný pro zpětnou kompatibilitu nebo pokud máte brány vrácení se změnami kódu na základě metrik kódu čísla. Příkaz k vytvoření *Metrics.exe* v režimu starší verze je:

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

Další informace najdete v tématu [povolit generování metriky kódu v režimu starší verze](https://github.com/dotnet/roslyn-analyzers/pull/1841).

### <a name="previous-versions"></a>Předchozí verze

Předchozí verze sady Visual Studio, včetně sady Visual Studio 2015, zahrnout metriky nástroj příkazového řádku kódu, který se také nazývá *Metrics.exe*. Tuto předchozí verzi nástroje nebylo binární analýzy, to znamená, analýzy založené na sestavení. Nový nástroj analyzuje zdrojový kód místo. Protože nové metriky nástroj příkazového řádku kódu je zdrojem založený na kódu, výsledky se liší na co je vygenerována v předchozích verzích nástroje *Metrics.exe* a integrovaného vývojového prostředí Visual Studio 2017.

Nový nástroj pro příkazový řádek kódu metriky vypočítá metriky i v případě výskytu chyby zdrojového kódu, za předpokladu, je možné načíst řešení a projektu.

#### <a name="metric-value-differences"></a>Rozdíly hodnota metriky

`LinesOfCode` Metrika je více přesným a spolehlivým v nové metriky nástroj příkazového řádku kódu. Je nezávislý na případné rozdíly codegen a nezmění, pokud se změní sadu nástrojů nebo modulu runtime. Nový nástroj počítá skutečné řádky kódu, včetně prázdné řádky a komentáře.

Jiné metriky, jako `CyclomaticComplexity` a `MaintainabilityIndex` stejné vzorce použít jako předchozí verze *Metrics.exe*, ale nový nástroj vypočítá počet `IOperations` (logické zdroj pokyny) namísto zprostředkující instrukcí jazyka (IL). Čísla budou mírně lišit od předchozích verzí *Metrics.exe* a z výsledků metrik kódu IDE sady Visual Studio 2017.

## <a name="see-also"></a>Viz také:

- [Použijte okno výsledků metrik kódu](../code-quality/working-with-code-metrics-data.md)
- [Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
