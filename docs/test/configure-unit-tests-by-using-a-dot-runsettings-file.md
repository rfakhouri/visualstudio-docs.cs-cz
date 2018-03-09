---
title: "Konfigurace testů jednotek v sadě Visual Studio pomocí *.runsettings* souboru | Microsoft Docs"
ms.date: 02/28/2018
ms.technology: vs-devops-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f10870096697341081904c4dac9540d72823e52f
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>Konfigurace testů jednotek pomocí *.runsettings* souboru

Testování částí v sadě Visual Studio můžete nakonfigurovat pomocí *.runsettings* souboru. Například můžete změnit verzi rozhraní .NET Framework, na kterém testy spouštějí, adresář pro výsledky testů nebo data shromážděná během spuštění testu.

> [!NOTE]
> Název souboru není důležité, tak dlouho, dokud používáte rozšíření '.runsettings'.

Pokud nevyžadujete žádnou zvláštní konfiguraci, nepotřebujete *.runsettings* souboru. Nejběžnější použití *.runsettings* soubor je k přizpůsobení [analýza pokrytí kódu](../test/customizing-code-coverage-analysis.md).

## <a name="customize-tests"></a>Přizpůsobit testy

1. Přidání souboru XML do řešení sady Visual Studio a přejmenujte ji na *test.runsettings*.

1. Nahraďte obsah souboru XML z příkladu, který následuje a přizpůsobit podle potřeby.

1. Na **Test** nabídce zvolte **nastavení testu** > **vyberte soubor s nastavením testu**.

Můžete vytvořit více než jeden *.runsettings* souborů ve vašem řešení a povolit nebo zakázat je v různou dobu pomocí **nastavení testu** nabídky.

![Povolení souboru parametrů běhu](../test/media/runsettings-1.png)

## <a name="example-runsettings-file"></a>Příklad *.runsettings* souboru

Toto je typické *.runsettings* souboru. Každý prvek souboru je volitelný, protože každá hodnota má výchozí nastavení.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
  <!-- Configurations that affect the Test Framework -->
  <RunConfiguration>
    <MaxCpuCount>1</MaxCpuCount>
    <!-- Path relative to solution directory -->
    <ResultsDirectory>.\TestResults</ResultsDirectory>

    <!-- x86 or x64
      - You can also change it from menu Test, Test Settings, Default Processor Architecture -->
    <TargetPlatform>x86</TargetPlatform>

    <!-- Framework35 | [Framework40] | Framework45 -->
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>

    <!-- Path to Test Adapters -->
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>
  
     <!--TestSessionTimeout is only available with Visual Studio 2017 version 15.5 and higher -->
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

*.Runsettings* soubor také slouží ke konfiguraci [analýza pokrytí kódu](../test/customizing-code-coverage-analysis.md).

Zbývající část tohoto článku popisuje obsah souboru.

## <a name="edit-your-runsettings-file"></a>Upravit vaše *.runsettings* souboru

V následujících podrobností elementy *.runsettings* souboru.

### <a name="test-run-configuration"></a>Konfigurace testovacího běhu

|Uzel|Výchozí|Hodnoty|
|----------|-------------|------------|
|`ResultsDirectory`||Adresář, kde jsou umístěny výsledky testů.|
|`TargetFrameworkVersion`|Framework40|Framework35, Framework40, Framework45<br /><br /> Toto nastavení určuje, která verze částí unit test framework se používá k zjišťování a spusťte testy. Může se lišit od verze platformy .NET, kterou jste zadali ve vlastnostech sestavení projektu testování částí.|
|`TargetPlatform`|x86|x86, x64|
|`TreatTestAdapterErrorsAsWarnings`|false|false, true|
|`TestAdaptersPaths`||Jednu nebo více cest k adresáři, kde se nachází TestAdapters|
|`MaxCpuCount`|1|Tato nastavení ovládacích prvků stupeň spuštění paralelní testu při testování částí spuštěné, pomocí jader dostupných na počítači. Spouštěcí modul testu se spustí jako odlišné proces v každém dostupné core a poskytuje každý základní kontejner s testy ke spuštění. Kontejner může být sestavení, knihovny DLL nebo relevantní artefaktů. Kontejner testů je plánování jednotka. V jednotlivých kontejnerech testy se spouštějí podle rozhraní test. Pokud existují mnoho kontejnerů, pak jako zpracovává dokončit provádění testů v kontejneru, jsou uvedeny další dostupné kontejneru.<br /><br /> MaxCpuCount může být:<br /><br /> n, kde 1 < = n < = počet jader: až n procesy bude spuštěna<br /><br /> n, kde n = jakoukoli jinou hodnotu: počet procesy spuštění bude až až k dispozici jádra na počítači|
|`TestSessionTimeout`||Umožňuje uživatelům ukončení relace testu, pokud se překročí daného časového limitu. Nastavení, které zajistí vypršení časového limitu a spotřebování prostředky a testovací relace jsou omezené na nastavte čas. Toto nastavení je k dispozici v **Visual Studio 2017 verze 15,5** a novější.

### <a name="diagnostic-data-adapters-data-collectors"></a>Adaptéry diagnostických dat (sběrače dat)

`DataCollectors` Element určuje nastavení dat diagnostiky adaptérů. Adaptérů diagnostických dat sbírat dodatečné informace o prostředí a aplikace v rámci testu. Každý adaptér má výchozí nastavení a budete muset zadat nastavení, pokud nechcete použít výchozí hodnoty.

#### <a name="code-coverage-adapter"></a>Adaptér pokrytí kódu

Kolektor dat pokrytí kódu vytvoří protokol uvádějící, které části kódu aplikace byly použity v testu. Další informace o přizpůsobení nastavení pro pokrytí kódu najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

#### <a name="video-data-collector"></a>Sběrač dat video

Kolekce video dat zaznamená obrazovky, zaznamenávání při spuštění testů. Tento záznam je užitečná pro řešení potíží s testy uživatelského rozhraní. Kolekce video dat je k dispozici v **Visual Studio 2017 verze 15,5** a novější.

Chcete-li přizpůsobit jakýkoli jiný typ adaptéru diagnostických dat, musíte použít soubor s nastavením testu. Další informace najdete v tématu [zadání nastavení testu pro testy Visual Studia](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests).

### <a name="testrunparameters"></a>TestRunParameters

TestRunParameters poskytuje způsob, jak definovat proměnných a hodnot, které jsou k dispozici pro testy za běhu. Tyto proměnné je přístupná pomocí [TestContext](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testcontext(v=vs.140).aspx) objektu.

```csharp
[TestMethod]
public void HomePageTest()
{
    string appURL = TestContext.Properties["webAppUrl"];
```

Chcete-li použít TestContext, přidejte privátního [TestContext](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testcontext(v=vs.140).aspx) pole a veřejné `TestContext` vlastnosti ke třídě testu.

### <a name="mstest-run-settings"></a>Parametry běhu adaptéru MSTest

Tato nastavení jsou specifické pro adaptér test, který spouští test metody, které mají `[TestMethod]` atribut.

|Konfigurace|Výchozí|Hodnoty|
|-------------------|-------------|------------|
|ForcedLegacyMode|false|V sadě Visual Studio 2012 bylo optimalizováno adaptér Mstestu zajistit rychlejší a větší škálovatelnost. Některé rysy chování sady, jako například pořadí, ve kterém jsou testy spuštěny, nemusí být přesně stejné jako v předchozích edicích sady Visual Studio. Nastavení této hodnoty `true` používat starší test adaptér.<br /><br /> Například můžete použít toto nastavení, pokud máte *app.config* soubor zadané pro testování částí.<br /><br /> Doporučujeme zvážit refaktoring testů, aby bylo možné použít novější adaptér.|
|IgnoreTestImpact|false|Funkce dopadu testu upřednostňuje při spuštění testů prostřednictvím adaptéru MSTest nebo nástroje Microsoft Test Manager testy, které jsou ovlivněny nedávnými změnami. Toto nastavení funkci deaktivuje. Další informace najdete v tématu [postupy: shromáždění dat pro kontrolu, které testy mají být spuštěny po změně kódu](http://msdn.microsoft.com/Library/2f921ea1-9bb0-4870-a30f-0521fc22cb47).|
|SettingsFile||Zde můžete určit soubor s nastavením testu, který chcete použít v adaptéru MSTest. Můžete také určit souborů nastavení testů pomocí nabídky **testování**, **Test nastavení**, **vyberte testovací soubor s nastaveními**.<br /><br /> Pokud zadáte tuto hodnotu, je nutné také nastavit **ForcedlegacyMode** k **true**.<br /><br /> `<RunSettings>   <MSTest>     <SettingsFile>my.testsettings</SettingsFile>      <ForcedLegacyMode>true</ForcedLegacyMode>    </MSTest> </RunSettings>`|
|KeepExecutorAliveAfterLegacyRun|false|Po dokončení běhu testu je adaptér MSTest vypnut. Jakýkoli proces, který je spuštěn jako součást test je také byly ukončeny. Pokud chcete zachovat prováděcí modul testování v provozu, přepněte tuto konfiguraci na hodnotu true.<br /><br /> Můžete například použít toto nastavení Pokud chcete zachovat v prohlížeči spuštění mezi programové testy uživatelského rozhraní.|
|DeploymentEnabled|true|Pokud hodnotu nastavíte na hodnotu false, položky nasazení, které jste zadali v metodu test se nezkopírují do adresáře nasazení.|
|CaptureTraceOutput|true|Pomocí příkazu Trace.WriteLine můžete zapisovat do trasování ladění z testovací metody. Pomocí této konfigurace můžete vypnout tato trasování ladění.|
|DeleteDeploymentDirectoryAfterTestRunIsComplete|true|Nastavením této hodnoty na false můžete po testovacím běhu zachovat adresář nasazení.|
|MapInconclusiveToFailed|false|Pokud se test vrátí v neprůkazném stavu, je obvykle v aplikaci Průzkumník testů mapován na stav Vynecháno. Pokud chcete testy neprůkazné zobrazený jako poškozený, použijte tuto konfiguraci.|
|InProcMode|false|Pokud chcete testy spouštět ve stejném procesu jako adaptér MSTest, nastavte tuto hodnotu na true. Toto nastavení poskytuje malé zvýšení výkonu. Pokud je však test ukončen výjimkou, nebudou ostatní testy pokračovat.|
|AssemblyResolution|false|Při hledání a spouštění testů jednotek můžete určit cest do dalších sestavení. Například použijte tyto cesty pro závislost sestavení, které není nacházet ve stejném adresáři jako testovací sestavení. Chcete-li zadat cestu, použijte element "Cesta k adresáři". Cesty může obsahovat proměnné prostředí.<br /><br /> `<AssemblyResolution>  <Directory Path="D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|

## <a name="see-also"></a>Viz také

[Přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md)
