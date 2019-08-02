---
title: Nejčastější dotazy k funkci Live Unit Testing
ms.date: 10/03/2017
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing FAQ
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 41d5248106b831accf4d71f97aeaeb72fdbc5018
ms.sourcegitcommit: 044bb54cb4552c8f4651feb11d62e52726117e75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2019
ms.locfileid: "68662025"
---
# <a name="live-unit-testing-frequently-asked-questions"></a>Live Unit Testing nejčastějších dotazech

## <a name="latest-features"></a>Nejnovější funkce

**Live Unit Testing se pravidelně vylepšuje a zvyšují. Jak najdu informace o nejnovějších nových funkcích a vylepšeních?**

Další informace o nových funkcích a vylepšeních, které jste provedli Live Unit Testing, najdete v článku [novinky v Live Unit Testing](live-unit-testing-whats-new.md).

## <a name="supported-frameworks-and-versions"></a>Podporované architektury a verze

**Jaké testovací architektury Live Unit Testing podporují a jaké jsou minimální podporované verze?**

Live Unit Testing pracuje se třemi oblíbenými platformami testování částí uvedenými v následující tabulce. Minimální podporovaná verze jejich adaptéry a rozhraní je také uvedený v tabulce. Rozhraní testování částí jsou všechny dostupné z webu NuGet.org.

|Rozhraní pro testování  |Minimální verze aplikace Visual Studio adaptéru  |Minimální verze rozhraní Framework  |
|---------|---------|---------|
|xUnit.net |verze 2.2.0-beta3-build1187 xunit.Runner.VisualStudio |1\.9.2 xunit |
|NUnit |NUnit3TestAdapter verze 3.7.0 |NUnit verze 3.5.0 |
|MSTest |MSTest.TestAdapter 1.1.4-preview |MSTest.TestFramework 1.0.5-preview |

Pokud máte starší projekty `Microsoft.VisualStudio.QualityTools.UnitTestFramework` testů založené na MSTest a nechcete přejít k novějším balíčkům NuGet MSTest, upgradujte na Visual Studio 2017 verze 15,4 nebo novější.

V některých případech budete muset explicitně obnovit balíčky NuGet odkazované projekty v řešení v pořadí pro Live Unit Testing pro práci. Balíčky můžete obnovit buď explicitním sestavením řešení (vyberte **sestavení**, znovu **Sestavit řešení** z nabídky nejvyšší úrovně), nebo kliknutím pravým tlačítkem na řešení a výběrem možnosti **obnovit balíčky NuGet** . povoluje testování živých jednotek.

## <a name="net-core-support"></a>Podpora .NET Core

**Funguje Live Unit Testing s .NET Core?**

Ano. Live Unit Testing funguje s .NET Core a .NET Framework. V aplikaci Visual Studio 2017 verze 15,3 byla přidána podpora .NET Core. Pokud chcete Live Unit Testing podporu pro .NET Core, upgradujte na tuto verzi sady Visual Studio nebo novější.

## <a name="configuration"></a>Konfiguraci

**Proč při zapínání neLive Unit Testing pracovat?**

V okně **výstup** (když se vybere rozevírací seznam Live Unit testing) by vám měl sdělit, proč Live Unit Testing nefunguje. Live Unit Testing nemusí fungovat z některého z následujících důvodů:

- Pokud balíčky NuGet odkazované projekty v řešení nebyly obnoveny, Live Unit Testing nebudou fungovat. Před zapnutím Live Unit Testing by měl tento problém vyřešit explicitní sestavení řešení nebo obnovení balíčků NuGet v řešení.

- Používáte-li v projektech testy založené na MSTest, nezapomeňte odebrat odkaz na `Microsoft.VisualStudio.QualityTools.UnitTestFramework`a přidat odkazy na nejnovější `MSTest.TestAdapter` balíčky MSTest NuGet (vyžaduje se minimálně verze 1.1.11) a `MSTest.TestFramework` (minimální verze je požadováno 1.1.11). Další informace naleznete v části "podporované testovací architektury" [v článku použití Live Unit Testing v aplikaci Visual Studio](live-unit-testing.md#supported-test-frameworks) .

- Nejméně jeden projekt ve vašem řešení by měl mít buď odkaz na NuGet, nebo přímý odkaz na rozhraní xUnit, NUnit nebo MSTest test Framework. Tento projekt by měl také odkazovat na odpovídající balíček NuGet testovacích adaptérů sady Visual Studio. Na testovací adaptér sady Visual Studio lze také odkazovat pomocí souboru *. runsettings* . Soubor *. runsettings* musí mít položku podobně jako v následujícím příkladu:

```xml
<RunSettings>
    <RunConfiguration>
          <TestAdaptersPaths>path-to-your-test-adapter</TestAdaptersPaths>
     </RunConfiguration>
</RunSettings>
```

## <a name="incorrect-coverage-after-upgrade"></a>Nesprávné pokrytí po upgradu

**Proč Live Unit Testing po upgradu testovacího adaptéru, na který se odkazuje v projektech Visual studia na podporovanou verzi, zobrazit nesprávné pokrytí?**

- Pokud více projektů v řešení odkazuje na balíček testovacího adaptéru NuGet, každá z nich musí být upgradována na podporovanou verzi.

- Ujistěte se, že soubor MSBuild *. props* importovaný z balíčku testovacího adaptéru je také správně aktualizován. Ověřte verzi balíčku NuGet nebo cestu k importu, která se obvykle nachází v horní části souboru projektu, jako je například následující:

   ```xml
    <Import Project="..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props" Condition="Exists('..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props')" />
   ```

## <a name="customize-builds"></a>Přizpůsobení sestavení

**Můžu přizpůsobit buildy Live Unit Testing?**

Pokud vaše řešení vyžaduje vlastní kroky k sestavení pro instrumentaci (Live Unit testing), které nejsou vyžadovány pro "normální" neinstrumentované sestavení, pak můžete přidat kód do projektu nebo *. cílící* na soubory, které kontrolují `BuildingForLiveUnitTesting` vlastnost a provede vlastní kroky před/po sestavení. Můžete také zvolit odebrání některých kroků sestavení (například publikování nebo generování balíčků) nebo přidání kroků sestavení (například zkopírování požadavků) do Live Unit Testing sestavení na základě této vlastnosti projektu. Přizpůsobení sestavení na základě této vlastnosti nemění vaše pravidelné sestavení jakýmkoli způsobem a má vliv pouze na Live Unit Testing sestavení.

Může se například jednat o cíl, který vytváří balíčky NuGet během pravidelného sestavování. Pravděpodobně nechcete generovat balíčky NuGet po každé úpravě, kterou provedete. Proto můžete tento cíl v Live Unit Testing sestavení zakázat následujícím způsobem:  

```xml
<Target Name="GenerateNuGetPackages" BeforeTargets="AfterBuild" Condition="'$(BuildingForLiveUnitTesting)' != 'true'">
    <Exec Command='"$(MSBuildThisFileDirectory)..\tools\GenPac" '/>
</Target>
```

## <a name="error-messages-with-ltoutputpathgt-or-ltoutdirgt"></a>Chybové zprávy s &lt;OutputPath&gt; nebo &lt;OutDir&gt;

**Proč se při Live Unit Testing pokusu o sestavení řešení zobrazí následující chyba: "... Zdá se, že se nepodmíněně `<OutDir>`nastaví `<OutputPath>` nebo. Live Unit Testing neprovede testy z výstupního sestavení?**

Tato chyba se může zobrazit, pokud proces sestavení pro vaše řešení nepodmíněně Přepisuje `<OutputPath>` nebo `<OutDir>` aby `<BaseOutputPath>`nebyl podadresářem. V takových případech Live Unit Testing nebude fungovat, protože také přepisuje tyto hodnoty, aby bylo zajištěno, že artefakty sestavení jsou vyřazeny do `<BaseOutputPath>`složky v rámci. Pokud je nutné přepsat umístění, kde mají být artefakty sestavení vyřazeny v běžném sestavení, přepište `<OutputPath>` podmíněně na `<BaseOutputPath>`základě.

Například pokud vaše sestavení přepíše, jak je `<OutputPath>` znázorněno níže:

```xml 
<Project>
  <PropertyGroup>
    <OutputPath>$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)</OutputPath>
  </PropertyGroup>
</Project>
```

pak ho můžete nahradit následujícím kódem XML:

```xml 
<Project>
  <PropertyGroup>
    <BaseOutputPath Condition="'$(BaseOutputPath)' == ''">$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)\</BaseOutputPath>
    <OutputPath Condition="'$(OutputPath)' == ''">$(BaseOutputPath)</OutputPath>
  </PropertyGroup>
</Project>
```

Tím se zajistí `<OutputPath>` , že se `<BaseOutputPath>` nachází ve složce.

Nepřepisujte `<OutDir>` přímo v procesu sestavení; místo toho `<OutputPath>` přepište, aby se artefakty sestavení vytlačily do konkrétního umístění.

## <a name="set-the-location-of-build-artifacts"></a>Nastavení umístění artefaktů sestavení

**Chci, aby artefakty Live Unit Testing sestavení přešly do konkrétního umístění namísto výchozího umístění ve složce *. vs* . Jak můžu změnit tuto možnost?**

Nastavte proměnnou prostředí na úrovni uživatelenacestu,kamchcetevyřaditartefaktysestaveníLiveUnitTesting.`LiveUnitTesting_BuildRoot` 

## <a name="test-explorer-vs-live-unit-testing-test-runs"></a>Průzkumník testů vs. Live Unit Testing testovací běhy

**Jak se spouští testy z okna Průzkumníka testů, se liší od spuštění testů v Live Unit Testing?**

Existuje několik rozdílů:

- Spuštění nebo ladění testů z okna **Průzkumníka testů** spouští běžné binární soubory, zatímco Live Unit Testing spouští instrumentované binární soubory. Pokud chcete ladit instrumentované binární soubory, přidejte [ladicí program.](xref:System.Diagnostics.Debugger.Launch) volání metody spuštění v testovací metodě způsobí, že se ladicí program spustí vždy, když se spustí Tato metoda (včetně okamžiku, kdy je spuštěna Live Unit testing), a pak můžete připojit a ladit instrumentované binární soubory. Ale doufáme, že je instrumentace pro většinu uživatelských scénářů transparentní a že nepotřebujete ladit instrumentované binární soubory.

- Live Unit Testing nevytváří novou doménu aplikace pro spuštění testů, ale testy spouštěné z okna **Průzkumník testů** vytvoří novou doménu aplikace.

- Live Unit Testing spouští testy v každém testovacím sestavení sekvenčně; v okně **Průzkumník testů** můžete zvolit paralelní spuštění více testů.

- Zjišťování a provádění testů v Live Unit Testing používá verzi 2 z `TestPlatform`, zatímco okno **Průzkumník testů** používá verzi 1. Ve většině případů si nevšimnete rozdílu.

- **Průzkumník testů** aktuálně ve výchozím nastavení spouští testy v modelu STA (Single-threaded Apartment), zatímco Live Unit Testing spouští testy ve vícevláknovém izolovaném modelu (MTA). Chcete-li spustit testy MSTest v modelu STA v Live Unit Testing, seupravte testovací metodu nebo obsahující `<STATestMethod>` třídu `<STATestClass>` atributem nebo, který `MSTest.STAExtensions 1.0.3-beta` lze najít v balíčku NuGet. Pro nunit seupravte testovací metodu s `<RequiresThread(ApartmentState.STA)>` atributem a pro xUnit `<STAFact>` s atributem.

## <a name="exclude-tests"></a>Vyloučit testy

**Návody vyloučit testy z účasti v Live Unit Testing?**

V části [použití Live Unit Testing v aplikaci Visual Studio](live-unit-testing.md#include-and-exclude-test-projects-and-test-methods) pro nastavení specifické pro uživatele naleznete informace v části "zahrnutí a vyloučení testovacích projektů a testovacích metod". Zahrnutí nebo vyloučení testů je užitečné, pokud chcete spustit konkrétní sadu testů pro určitou relaci úprav nebo zachovat vlastní osobní preference.

Pro konkrétní řešení můžete <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute?displayProperty=fullName> atribut použít programově pro vyloučení metod, vlastností, tříd nebo struktur z instrumentace pomocí Live Unit Testing. Kromě toho můžete také nastavit `<ExcludeFromCodeCoverage>` vlastnost na `true` v souboru projektu tak, aby se vyloučil celý projekt z instrumentace. Live Unit Testing bude stále spouštět testy, které nebyly instrumentované, ale jejich pokrytí nebude vizuálně fungovat.

Můžete také ověřit, zda `Microsoft.CodeAnalysis.LiveUnitTesting.Runtime` je načtena v aktuální doméně aplikace, a zakázat testy založené na tom, proč. Pomocí xUnit můžete například udělat něco podobného jako následující:

```csharp
[ExcludeFromCodeCoverage]
public class SkipLiveFactAttribute : FactAttribute
{
   private static bool s_lutRuntimeLoaded = AppDomain.CurrentDomain.GetAssemblies().Any(a => a.GetName().Name ==
                                            "Microsoft.CodeAnalysis.LiveUnitTesting.Runtime");
   public override string Skip => s_lutRuntimeLoaded ? "Test excluded from Live Unit Testing" : "";
}

public class Class1
{
   [SkipLiveFact]
   public void F()
   {
      Assert.True(true);
   }
}
```

## <a name="win32-pe-headers"></a>Hlavičky Win32 PE

**Proč se záhlaví Win32 PE liší v instrumentovaná sestavení vytvořená za provozu Live Unit Testing?**

Tento problém je vyřešen a neexistuje v aplikaci Visual Studio 2017 verze 15,3 a novější.

Pro starší verze sady Visual Studio 2017 existuje známá chyba, která může způsobit, že se sestavení Live Unit Testing nedaří vložit následující data hlavičky Win32 PE:

- Verze souboru (určená @System.Reflection.AssemblyFileVersionAttribute v kódu).

- Ikona Win32 (určená `/win32icon:` v příkazovém řádku).

- Manifest Win32 (určený `/win32manifest:` v příkazovém řádku).

Testy, které spoléhají na tyto hodnoty, mohou být při spuštění službou Live Unit Tests neúspěšné.

## <a name="continuous-builds"></a>Průběžná sestavení

**Proč živý test jednotek neustále sestavuje řešení i v případě, že neprovádíte žádné úpravy?**

Vaše řešení může sestavit i v případě, že neprovádíte úpravy, pokud proces sestavení vašeho řešení generuje zdrojový kód, který je součástí samotného řešení, a cílové soubory sestavení nemají odpovídající vstupy a výstupy. Cílům by měl být uveden seznam vstupů a výstupů, aby nástroj MSBuild mohl provádět příslušné kontroly a určit, zda je vyžadováno nové sestavení.

Live Unit Testing spustí sestavení pokaždé, když zjistí, že se změnily zdrojové soubory. Vzhledem k tomu, že sestavení vašeho řešení generuje zdrojové soubory, Live Unit Testing se dostane do nekonečné smyčky sestavení. Pokud jsou však vstupy a výstupy cíle zkontrolovány, když Live Unit Testing spustí druhé sestavení (po zjištění nově vygenerovaných zdrojových souborů z předchozího sestavení), dojde k přerušení smyčky sestavení, protože kontroly vstupů a výstupů bude označuje, že vše je aktuální.  

## <a name="new-process-coverage"></a>Nové pokrytí procesu

**Proč neLive Unit Testing zachytávání pokrytí z nového procesu vytvořeného testem?**

Jedná se o známý problém a měl by být opraven v pozdější verzi.

## <a name="including-or-excluding-tests-doesnt-work"></a>Zahrnutí nebo vyloučení testů nefunguje

**Proč k tomu nedojde po zahrnutí nebo vyloučení testů ze sady Live test?**

Tento problém je vyřešen a neexistuje v aplikaci Visual Studio 2017 verze 15,3 a novější.

Pro starší verze sady Visual Studio 2017 se jedná o známý problém. Pokud chcete tento problém obejít, budete muset provést úpravu libovolného souboru po zahrnutí nebo vyloučení testů.

## <a name="editor-icons"></a>Ikony editoru

**Proč v editoru nevidím žádné ikony, i když Live Unit Testing zdá spustit testy na základě zpráv v okně výstup?**

V editoru se nemusí zobrazovat ikony, pokud sestavení, na kterých Live Unit Testing pracuje, nejsou z nějakého důvodu instrumentovaná. Například Live Unit Testing není kompatibilní s projekty, které jsou nastaveny `<UseHostCompilerIfAvailable>false</UseHostCompilerIfAvailable>`. V takovém případě je potřeba aktualizovat proces sestavení, aby toto nastavení buď odebralo, nebo bylo možné ho `true` změnit, aby Live Unit Testing fungovalo. 

## <a name="capture-logs"></a>Zaznamenat protokoly

**Návody shromažďovat podrobnější protokoly o chybách souborů?**

K shromažďování podrobnějších protokolů můžete provést několik věcí:

- Přejděte na > **Možnosti** nástroje Live Unit Testing a změňte možnost protokolování na Verbose. >  Podrobné protokolování způsobí, že se v okně **výstup** Zobrazí podrobnější protokoly.

- Nastavte proměnnou prostředí uživatele na název souboru, který chcete použít k zachycení protokolu MSBuild. `LiveUnitTesting_BuildLog` Podrobné zprávy protokolu MSBuild z Live Unit Testing sestavení je možné z tohoto souboru načíst.

- Nastavte proměnnou prostředí `1`uživatelena hodnotu pro zachycení protokolu testovací platformy. `LiveUnitTesting_TestPlatformLog` Podrobné zprávy protokolu testovací platformy z Live Unit Testing spuštění lze následně načíst z `[Solution Root]\.vs\[Solution Name]\log\[VisualStudio Process ID]`.

- Vytvořte proměnnou prostředí na úrovni uživatele s názvem `VS_UTE_DIAGNOSTICS` a nastavte ji na 1 (nebo libovolnou hodnotu) a restartujte Visual Studio. Nyní byste měli vidět spoustu protokolování na kartě **výstupní-testy** v aplikaci Visual Studio.

## <a name="see-also"></a>Viz také:

- [Živé testování částí](live-unit-testing.md)
