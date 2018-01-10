---
title: "Konfigurace testů jednotek s použitím souboru .runsettings | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 1925152f830d9969c8650fe698be6ebc70e65cf2
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="configure-unit-tests-by-using-a-runsettings-file"></a>Konfigurace testů jednotek s použitím souboru .runsettings

Testování částí v sadě Visual Studio můžete nakonfigurovat pomocí \*souboru .runsettings. (Název souboru není důležité, pokud použijete rozšíření '.runsettings'.) Například můžete změnit verzi rozhraní .NET Framework na kterém bude spouštět testy, adresář, kde se dodávají výsledky testů, a spusťte data shromážděná během testu.

Pokud nevyžadujete žádnou zvláštní konfiguraci, nepotřebujete \*souboru .runsettings. Nejběžnější použití \*souboru .runsettings je přizpůsobit [pokrytí kódu](../test/customizing-code-coverage-analysis.md).

## <a name="customizing-tests-with-a-runsettings-file"></a>Přizpůsobení testů pomocí souboru .runsettings

1. Přidání souboru XML do řešení sady Visual Studio a přejmenujte jej na test.runsettings. (Název souboru není důležité, ale přípona musí být .runsettings.)

1. Nahraďte obsah souboru XML z příkladu, který následuje a přizpůsobit podle potřeby.

1. Na **Test** nabídce zvolte **nastavení testu** > **vyberte soubor s nastavením testu**.

Můžete vytvořit více než jeden \*.runsettings souborů ve vašem řešení a povolit nebo zakázat je v různou dobu pomocí **nastavení testu** nabídky.

![Povolení souboru parametrů běhu](../test/media/runsettings-1.png "RunSettings-1")

## <a name="example-runsettings-file"></a>Příklad souboru .runsettings

Toto je typické \*souboru .runsettings. Každý prvek souboru je volitelný, protože každá hodnota má výchozí nastavení.

```xml
<?xml version="1.0" encoding="utf-8"?>  
<RunSettings>  
  <!-- Configurations that affect the Test Framework -->  
  <RunConfiguration>  
    <MaxCpuCount>1</MaxCpuCount>  
    <!-- Path relative to solution directory -->  
    <ResultsDirectory>.\TestResults</ResultsDirectory>  
  
    <!-- [x86] | x64    
      - You can also change it from menu Test, Test Settings, Default Processor Architecture -->  
    <TargetPlatform>x86</TargetPlatform>  
  
    <!-- Framework35 | [Framework40] | Framework45 -->  
    <TargetFrameworkVersion>Framework40</TargetFrameworkVersion>  
  
    <!-- Path to Test Adapters -->  
    <TestAdaptersPaths>%SystemDrive%\Temp\foo;%SystemDrive%\Temp\bar</TestAdaptersPaths>  
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
  
Souboru .runsettings také slouží ke konfiguraci [pokrytí kódu](../test/customizing-code-coverage-analysis.md).  
  
Zbývající část tohoto tématu popisuje obsah souboru.  

## <a name="edit-your-runsettings-file"></a>Úprava souboru .runsettings

Soubor .runsettings obsahuje následující prvky.

### <a name="test-run-configuration"></a>Konfigurace testovacího běhu

|Uzel|Výchozí|Hodnoty|  
|----------|-------------|------------|  
|`ResultsDirectory`||Adresář, kde budou umístěny výsledky testů.|  
|`TargetFrameworkVersion`|Framework40|Framework35, Framework40, Framework45<br /><br /> Toto určuje, která verze rozhraní pro testování částí slouží k zjištění a provedení testů. Může se lišit od verze platformy .NET, kterou jste zadali ve vlastnostech sestavení projektu testování částí.|  
|`TargetPlatform`|x86|x86, x64|  
|`TreatTestAdapterErrorsAsWarnings`|false|false, true|  
|`TestAdaptersPaths`||Jednu nebo více cest k adresáři, kde se nachází TestAdapters|  
|`MaxCpuCount`|1|Tento ovládací prvky stupeň spuštění paralelní testu při spuštění jednotky testování s využitím dostupné jader na počítači.  Spouštěcí modul testu spustí jako odlišné proces v každém dostupné core a poskytuje každý základní kontejner s testy, které chcete spustit, jako je sestavení, knihovny DLL nebo relevantní artefaktů.  Kontejner testů je plánování jednotka.  V jednotlivých kontejnerech testy se spouštějí podle rozhraní test.  Pokud existují mnoho kontejnerů, pak jako zpracovává dokončit provádění testů v kontejneru, jsou uvedeny další dostupné kontejneru.<br /><br /> MaxCpuCount může být:<br /><br /> n, kde 1 < = n < = počet jader: až n procesy bude spuštěna<br /><br /> n, kde n = jakoukoli jinou hodnotu: počet procesy spuštění bude až až k dispozici jádra na počítači|  
  
### <a name="diagnostic-data-adapters-data-collectors"></a>Adaptéry diagnostických dat (sběrače dat)

`DataCollectors` Element určuje nastavení dat diagnostiky adaptérů. Adaptéry diagnostických dat slouží k získání dalších informací o testovaném prostředí a aplikaci. Každý adaptér má výchozí nastavení a budete muset zadat nastavení, pokud nechcete použít výchozí hodnoty.

#### <a name="code-coverage-adapter"></a>Adaptér pokrytí kódu

Kolektor dat pokrytí kódu vytvoří protokol uvádějící, které části kódu aplikace byly použity v testu. Další informace o přizpůsobení nastavení pro pokrytí kódu najdete v tématu [přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md).

### <a name="testrunparameters"></a>TestRunParameters

TestRunParameters poskytuje způsob, jak definovat proměnných a hodnot, které jsou k dispozici pro testy za běhu.  

### <a name="mstest-run-settings"></a>Parametry běhu adaptéru MSTest

Tato nastavení jsou specifické pro adaptér test, který spouští test metody, které mají `[TestMethod]` atribut.  

|Konfigurace|Výchozí|Hodnoty|  
|-------------------|-------------|------------|  
|ForcedLegacyMode|false|V sadě Visual Studio 2012 byl optimalizován adaptér MSTest tak, aby byl rychlejší a lépe škálovatelný. Některé rysy chování sady, jako například pořadí, ve kterém jsou testy spuštěny, nemusí být přesně stejné jako v předchozích edicích sady Visual Studio. Nastavení této hodnoty `true` používat starší test adaptér.<br /><br /> Toto nastavení můžete například použít, pokud máte pro testování částí určen soubor app.config.<br /><br /> Doporučujeme zvážit refaktoring testů, aby bylo možné použít novější adaptér.|  
|IgnoreTestImpact|false|Funkce dopadu testu upřednostňuje při spuštění testů prostřednictvím adaptéru MSTest nebo nástroje Microsoft Test Manager testy, které jsou ovlivněny nedávnými změnami. Toto nastavení funkci deaktivuje. Další informace najdete v tématu [postupy: shromáždění dat pro kontrolu, které testy mají být spuštěny po změně kódu](http://msdn.microsoft.com/Library/2f921ea1-9bb0-4870-a30f-0521fc22cb47).|  
|SettingsFile||Zde můžete určit soubor s nastavením testu, který chcete použít v adaptéru MSTest. Můžete také určit souborů nastavení testů pomocí nabídky **testování**, **Test nastavení**, **vyberte testovací soubor s nastaveními**.<br /><br /> Pokud zadáte tuto hodnotu, je nutné také nastavit **ForcedlegacyMode** k **true**.<br /><br /> `<RunSettings>   <MSTest>     <SettingsFile>my.testsettings</SettingsFile>      <ForcedLegacyMode>true</ForcedLegacyMode>    </MSTest> </RunSettings>`|  
|KeepExecutorAliveAfterLegacyRun|false|Po dokončení běhu testu je adaptér MSTest vypnut. Jakýkoli proces, který je spuštěn jako část testu, bude v tuto chvíli také ukončen. Pokud chcete zachovat prováděcí modul testování v provozu, přepněte tuto konfiguraci na hodnotu true.<br /><br /> Toto nastavení můžete například použít pro zachování chodu prohlížeče mezi programovými testy uživatelského rozhraní.|  
|DeploymentEnabled|true|Pokud nastavíte hodnotu false, nezkopírují se položky nasazení, které jste určili v testovací metodě, do adresáře nasazení.|  
|CaptureTraceOutput|true|Pomocí příkazu Trace.WriteLine můžete zapisovat do trasování ladění z testovací metody. Pomocí této konfigurace můžete vypnout tato trasování ladění.|  
|DeleteDeploymentDirectoryAfterTestRunIsComplete|true|Nastavením této hodnoty na false můžete po testovacím běhu zachovat adresář nasazení.|  
|MapInconclusiveToFailed|false|Pokud se test vrátí v neprůkazném stavu, je obvykle v aplikaci Průzkumník testů mapován na stav Vynecháno. Pokud chcete, aby se neprůkazné testy zobrazovaly ve stavu Selhalo, je třeba použít tuto konfiguraci.|  
|InProcMode|false|Pokud chcete testy spouštět ve stejném procesu jako adaptér MSTest, nastavte tuto hodnotu na true. Toto nastavení poskytuje malé zvýšení výkonu. Pokud je však test ukončen výjimkou, nebudou ostatní testy pokračovat.|  
|AssemblyResolution|false|Při hledání a spouštění testů jednotek můžete určit cest do dalších sestavení.  Například použijte tyto cesty pro závislost sestavení, které není nacházet ve stejném adresáři jako testovací sestavení.  Chcete-li zadat cestu, použijte element "Cesta k adresáři".  Cesty může obsahovat proměnné prostředí.<br /><br /> `<AssemblyResolution>  <Directory Path>"D:\myfolder\bin\" includeSubDirectories="false"/> </AssemblyResolution>`|  

## <a name="see-also"></a>Viz také

[Přizpůsobení analýzy pokrytí kódu](../test/customizing-code-coverage-analysis.md)  
