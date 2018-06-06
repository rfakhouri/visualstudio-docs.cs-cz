---
title: Konfigurace testů jednotek pomocí souboru .runsettings
ms.date: 02/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f0cb4989877445a0679a5682aaa17e4b7f759a33
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815974"
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>Konfigurace testů jednotek pomocí *.runsettings* souboru

Testování částí v sadě Visual Studio můžete nakonfigurovat pomocí *.runsettings* souboru. Například můžete změnit verzi rozhraní .NET Framework, na kterém testy spouštějí, adresář pro výsledky testů nebo data shromážděná během spuštění testu.

Soubory parametrů běhu jsou volitelné. Pokud nevyžadujete žádnou zvláštní konfiguraci, nepotřebujete *.runsettings* souboru. Nejběžnější použití *.runsettings* soubor je k přizpůsobení [analýza pokrytí kódu](../test/customizing-code-coverage-analysis.md).

## <a name="specify-a-run-settings-file"></a>Zadejte soubor parametrů běhu

Spustit soubory můžete použít ke konfiguraci testy, které jsou spouštěny z příkazového řádku v prostředí IDE, nebo v nastavení [sestavení pracovního postupu](/vsts/pipelines/test/getting-started-with-continuous-testing?view=vsts) pomocí Visual Studio Team Services (VSTS) nebo Team Foundation Server (TFS).

### <a name="specify-a-run-settings-file-in-the-ide"></a>Zadejte soubor parametrů běhu v prostředí IDE

Vyberte **Test** > **nastavení testu** > **vyberte soubor s nastavením testu** a pak vyberte *.runsettings*souboru. Soubor se zobrazí na **nastavení testu** nabídce a můžete vybrat nebo ji zrušte. Po výběru souboru parametrů běhu platí vždy, když vyberete **analýza pokrytí kódu**.

![Vyberte nabídku souborů nastavení testů v sadě Visual Studio](media/select-test-settings-file.png)

### <a name="specify-a-run-settings-file-at-the-command-line"></a>Zadejte nastavení spuštění soubor na příkazovém řádku

Ke spuštění testů z příkazového řádku, použijte *vstest.console.exe* a určete soubor nastavení pomocí **/Settings** parametr.

1. Spusťte příkazový řádek pro vývojáře v sadě Visual Studio:

   V systému Windows **spustit** nabídce zvolte **Visual Studio 2017** > **příkazový řádek vývojáře pro VS 2017**.

2. Zadejte příkaz podobný:

   ```cmd
   vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage /Settings:CodeCoverage.runsettings
   ```

## <a name="customize-tests"></a>Přizpůsobit testy

Chcete-li přizpůsobit testy pomocí *.runsettings* souboru, postupujte takto:

1. Přidání souboru XML do řešení sady Visual Studio a uložte ho jako *test.runsettings*.

   > [!TIP]
   > Název souboru není důležité, tak dlouho, dokud pomocí rozšíření *.runsettings*.

1. Nahraďte obsah souboru XML z příkladu, který následuje a přizpůsobit podle potřeby.

1. Na **Test** nabídce zvolte **nastavení testu** > **vyberte soubor s nastavením testu**. Vyhledejte *.runsettings* souboru, kterou jste vytvořili a potom vyberte **OK**.

   > [!TIP]
   > Můžete vytvořit více než jeden *.runsettings* souborů ve vašem řešení a vyberte jednu jako soubor active testovací nastavení podle potřeby.

## <a name="example-runsettings-file"></a>Příklad *.runsettings* souboru

Následující kód XML zobrazí obsah typické *.runsettings* souboru. Každý prvek souboru je volitelný, protože má výchozí hodnotu.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
  <!-- Configurations that affect the Test Framework -->
  <RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <!-- Path relative to solution directory -->
    <ResultsDirectory>.\TestResults</ResultsDirectory>

    <!-- x86 or x64 -->
    <!-- You can also change it from menu Test > Test Settings > Default Processor Architecture -->
    <TargetPlatform>x86</TargetPlatform>

    <!-- Framework35 | [Framework40] | Framework45 -->
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>

    <!-- Path to Test Adapters -->
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>

    <!-- TestSessionTimeout is only available with Visual Studio 2017 version 15.5 and higher -->
    <!-- Specify timeout in milliseconds. A valid value should be greater than 0 -->
    <TestSessionTimeout>10000</TestSessionTimeout>
  </RunConfiguration>

  <!-- Configurations for data collectors -->
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">
        <Configuration>
          <CodeCoverage>
            <ModulePaths>
              <Exclude>
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
              </Exclude>
            </ModulePaths>

            <!-- We recommend you do not change the following values: -->
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
            <CollectFromChildProcesses>True</CollectFromChildProcesses>
            <CollectAspDotNet>False</CollectAspDotNet>

          </CodeCoverage>
        </Configuration>
      </DataCollector>

      <!--Video data collector is only available with Visual Studio 2017 version 15.5 and higher -->
      <DataCollector uri="datacollector://microsoft/VideoRecorder/1.0" assemblyQualifiedName="Microsoft.VisualStudio.TestTools.DataCollection.VideoRecorder.VideoRecorderDataCollector, Microsoft.VisualStudio.TestTools.DataCollection.VideoRecorder, Version=15.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" friendlyName="Screen and Voice Recorder">
      </DataCollector>

    </DataCollectors>
  </DataCollectionRunSettings>

  <!-- Parameters used by tests at runtime -->
  <TestRunParameters>
    <Parameter name="webAppUrl" value="http://localhost" />
    <Parameter name="webAppUserName" value="Admin" />
    <Parameter name="webAppPassword" value="Password" />
  </TestRunParameters>

  <!-- Adapter Specific sections -->

  <!-- MSTest adapter -->
  <MSTest>
    <MapInconclusiveToFailed>True</MapInconclusiveToFailed>
    <CaptureTraceOutput>false</CaptureTraceOutput>
    <DeleteDeploymentDirectoryAfterTestRunIsComplete>False</DeleteDeploymentDirectoryAfterTestRunIsComplete>
    <DeploymentEnabled>False</DeploymentEnabled>
    <AssemblyResolution>
      <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/>
    </AssemblyResolution>
  </MSTest>

</RunSettings>
```

## <a name="elements-of-a-runsettings-file"></a>Elementy *.runsettings* souboru

V následujících podrobností elementy *.runsettings* souboru.

### <a name="run-configuration"></a>Spuštění nástroje Konfigurace

```xml
<RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <ResultsDirectory>.\TestResults</ResultsDirectory>
    <TargetPlatform>x86</TargetPlatform>
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>
    <TestSessionTimeout>10000</TestSessionTimeout>
</RunConfiguration>
```

**RunConfiguration** element může obsahovat následující prvky:

|Uzel|Výchozí|Hodnoty|
|----------|-------------|------------|
|**ResultsDirectory**||Adresář, kde jsou umístěny výsledky testů.|
|**targetFrameworkVersion**|Framework40|Framework35, Framework40, Framework45<br /><br />Toto nastavení určuje, která verze částí unit test framework se používá k zjišťování a spusťte testy. Může se lišit od verze platformy .NET, kterou jste zadali ve vlastnostech sestavení projektu testování částí.|
|**TargetPlatform**|x86|x86, x64|
|**TreatTestAdapterErrorsAsWarnings**|false|false, true|
|**TestAdaptersPaths**||Jednu nebo více cest k adresáři, kde se nachází TestAdapters|
|**MaxCpuCount**|1|Tato nastavení ovládacích prvků stupeň spuštění paralelní testu při testování částí spuštěné, pomocí jader dostupných na počítači. Spouštěcí modul testu se spustí jako odlišné proces v každém dostupné core a poskytuje každý základní kontejner s testy ke spuštění. Kontejner může být sestavení, knihovny DLL nebo relevantní artefaktů. Kontejner testů je plánování jednotka. V jednotlivých kontejnerech testy se spouštějí podle rozhraní test. Pokud existují mnoho kontejnerů, pak jako zpracovává dokončit provádění testů v kontejneru, jste, získá další dostupné kontejneru.<br /><br />MaxCpuCount může být:<br /><br />n, kde 1 < = n < = počet jader: až n procesy spuštění<br /><br />n, kde n = jakoukoli jinou hodnotu: počet spuštění procesů může být maximálně počet dostupných jader|
|**TestSessionTimeout**||Umožňuje uživatelům ukončení relace testu, pokud se překročí daného časového limitu. Nastavení, které zajistí vypršení časového limitu a spotřebování prostředky a testovací relace jsou omezené na nastavte čas. Toto nastavení je k dispozici v **Visual Studio 2017 verze 15,5** a novější.|

### <a name="diagnostic-data-adapters-data-collectors"></a>Adaptérů diagnostických dat (sběrače dat)

**DataCollectors** element určuje nastavení dat diagnostiky adaptérů. Adaptérů diagnostických dat sbírat dodatečné informace o prostředí a aplikace v rámci testu. Každý adaptér má výchozí nastavení a budete muset zadat nastavení, pokud nechcete použít výchozí hodnoty.

#### <a name="code-coverage-adapter"></a>Adaptér pokrytí kódu

```xml
<CodeCoverage>
    <ModulePaths>
        <Exclude>
            <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
        </Exclude>
    </ModulePaths>

    <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
    <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
    <CollectFromChildProcesses>True</CollectFromChildProcesses>
    <CollectAspDotNet>False</CollectAspDotNet>
</CodeCoverage>
```

Kolektor dat pokrytí kódu vytvoří protokol uvádějící, které části kódu aplikace byly použity v testu. Další informace o přizpůsobení nastavení pro pokrytí kódu najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

#### <a name="video-data-collector"></a>Sběrač dat video

Kolekce video dat zaznamená obrazovky, zaznamenávání při spuštění testů. Tento záznam je užitečná pro řešení potíží s testy uživatelského rozhraní. Kolekce video dat je k dispozici v **Visual Studio 2017 verze 15,5** a novější.

Chcete-li přizpůsobit žádný jiný druh adaptérů diagnostických dat, použijte [soubor s nastavením testu](../test/collect-diagnostic-information-using-test-settings.md).

### <a name="testrunparameters"></a>TestRunParameters

```xml
<TestRunParameters>
    <Parameter name="webAppUrl" value="http://localhost" />
    <Parameter name="webAppUserName" value="Admin" />
    <Parameter name="webAppPassword" value="Password" />
</TestRunParameters>
```

Parametry testu poskytují způsob, jak definovat proměnných a hodnot, které jsou k dispozici pro testy za běhu. Přístup k parametry, pomocí <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.Properties%2A?displayProperty=nameWithType> vlastnost:

```csharp
[TestMethod]
public void HomePageTest()
{
    string appURL = TestContext.Properties["webAppUrl"];
```

Pokud chcete používat parametry testu, spuštění, přidejte privátního <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> pole a veřejné <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> vlastnosti ke třídě testu.

### <a name="mstest-run-settings"></a>Mstestu parametry spuštění

```xml
<MSTest>
    <MapInconclusiveToFailed>True</MapInconclusiveToFailed>
    <CaptureTraceOutput>false</CaptureTraceOutput>
    <DeleteDeploymentDirectoryAfterTestRunIsComplete>False</DeleteDeploymentDirectoryAfterTestRunIsComplete>
    <DeploymentEnabled>False</DeploymentEnabled>
    <AssemblyResolution>
      <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/>
    </AssemblyResolution>
</MSTest
```

Tato nastavení jsou specifické pro adaptér test, který spouští test metody, které mají <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> atribut.

|Konfigurace|Výchozí|Hodnoty|
|-------------------|-------------|------------|
|**ForcedLegacyMode**|false|V sadě Visual Studio 2012 bylo optimalizováno adaptér Mstestu zajistit rychlejší a větší škálovatelnost. Některé rysy chování sady, jako například pořadí, ve kterém jsou testy spuštěny, nemusí být přesně stejné jako v předchozích edicích sady Visual Studio. Nastavte tuto hodnotu na **true** používat starší test adaptér.<br /><br />Například můžete použít toto nastavení, pokud máte *app.config* soubor zadané pro testování částí.<br /><br />Doporučujeme zvážit refaktoring testů, aby bylo možné použít novější adaptér.|
|**IgnoreTestImpact**|false|Funkce dopadu testu upřednostňuje při spuštění testů prostřednictvím adaptéru MSTest nebo nástroje Microsoft Test Manager testy, které jsou ovlivněny nedávnými změnami. Toto nastavení funkci deaktivuje. Další informace najdete v tématu [které testy je třeba spustit od předchozího sestavení](https://msdn.microsoft.com/library/dd286589).|
|**Soubor_nastavení**||Můžete zadat souboru nastavení testů pro použití s Mstestu adaptéru v tomto poli. Můžete taky zadat souborů nastavení testů výběrem **testování** > **Test nastavení** > **vyberte testovací soubor s nastaveními**.<br /><br />Pokud zadáte tuto hodnotu, je nutné také nastavit **ForcedlegacyMode** k **true**.<br /><br />`<ForcedLegacyMode>true</ForcedLegacyMode>`|
|**KeepExecutorAliveAfterLegacyRun**|false|Po dokončení běhu testu je adaptér MSTest vypnut. Jakýkoli proces, který je spuštěn jako součást test je také byly ukončeny. Pokud chcete zachovat vykonavatele testovací aktivní, nastavte hodnotu na **true**. Můžete například použít toto nastavení Pokud chcete zachovat v prohlížeči spuštění mezi programové testy uživatelského rozhraní.|
|**DeploymentEnabled**|true|Pokud nastavíte hodnotu na **false**, nasazení položky, které jste určili ve své metodě testovací nejsou zkopírovat do adresáře nasazení.|
|**CaptureTraceOutput**|true|Je možné zapsat do trasování ladění z pomocí metoda testovací <xref:System.Diagnostics.Trace.WriteLine%2A?displayProperty=nameWithType>.|
|**DeleteDeploymentDirectoryAfterTestRunIsComplete**|true|Pokud chcete zachovat adresáře nasazení po spuštění testu, nastavte hodnotu **false**.|
|**MapInconclusiveToFailed**|false|V případě, test skončí s neprůkazné stav, je namapovaný na přeskočené stav v **testování Explorer**. Pokud chcete testy neprůkazné zobrazený jako neúspěšná, nastavte hodnotu na **true**.|
|**InProcMode**|false|Pokud chcete testů ke spuštění v rámci jednoho procesu, jako je adaptér Mstestu, nastavte hodnotu **true**. Toto nastavení poskytuje malé zvýšení výkonu. Ale pokud testu ukončení s výjimkou zbývající testy nespouštět.|
|**AssemblyResolution**|false|Při hledání a spouštění testů jednotek můžete určit cest do dalších sestavení. Například použijte tyto cesty pro závislost sestavení, které nejsou ve stejném adresáři jako testovací sestavení. Pokud chcete zadat cestu, použijte **cesta k adresáři** elementu. Cesty může obsahovat proměnné prostředí.<br /><br />`<AssemblyResolution>  <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|

## <a name="see-also"></a>Viz také:

- [Přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md)
- [Visual Studio Test úloh (VSTS)](/vsts/pipelines/tasks/test/vstest?view=vsts)