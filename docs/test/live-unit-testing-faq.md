---
title: "Nejčastější dotazy k testování částí Live | Microsoft Docs"
ms.date: 2017-10-03
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing FAQ
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 2437a138e9e83d3b723971b53dac413ad0ea4151
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="live-unit-testing-frequently-asked-questions"></a>Live testování částí nejčastější dotazy

## <a name="live-unit-testing-is-improved-and-enhanced-regularly-how-can-i-find-information-about-the-latest-new-features-and-enhancements"></a>Testování částí za provozu je vylepšené a rozšířené pravidelně. Jak může najít informace o nejnovější nových funkcích a vylepšeních?

**Odpověď:**

Další informace o nových funkcích a vylepšeních, které byly provedeny na Live testování částí od verze Visual Studio 2017 verze 15.3 najdete v tématu [co je nového v za provozu testování částí](live-unit-testing-whats-new.md).


## <a name="what-test-frameworks-does-live-unit-testing-support-and-what-are-the-minimum-supported-versions"></a>Jaké systémů testování podporuje Live testování částí podporu a jaké jsou minimální podporované verze?

**Odpověď:**

Za provozu testování částí funguje s tři architektury testování oblíbených jednotky uvedené v následující tabulce. Minimální podporovaná verze jejich adaptérů a architektury je také uvedené v tabulce. Jsou všechny dostupné z NuGet.org architektury testování jednotky.

<table>
<tr>
   <th>Test Framework</th>
   <th>Visual Studio adaptér minimální verze</th>
   <th>Minimální verze Framework</th>
</tr>
<tr>
   <td>xUnit.net</td>
   <td> xunit.runner.visualstudio version 2.2.0-beta3-build1187</td>
   <td>xunit 1.9.2</td>
</tr>
<tr>
   <td>NUnit</td>
   <td>NUnit3TestAdapter verzí 3.5.1</td>
   <td>NUnit verze 3.5.0</td>
</tr>
<tr>
   <td>MSTest</td>
   <td>MSTest.TestAdapter 1.1.4-preview</td>
   <td>MSTest.TestFramework 1.0.5-preview</td>
</tr>
</table>

Pokud máte starší Mstestu na základě testovací projekty tento odkaz `Microsoft.VisualStudio.QualityTools.UnitTestFramework` a můžete si jej nepřejete přesunout do novější balíčky NuGet Mstestu, upgradujte na verzi Visual Studio 2017 verzi 15.4.

V některých případech budete muset explicitně obnovování balíčků NuGet odkazuje projekty v řešení v pořadí pro Live testování částí pro práci. Musíte buď pomocí tohoto postupu explicitní sestavení řešení (vyberte **sestavení**, **znovu sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio) nebo obnovují se balíčky v řešení (klikněte pravým tlačítkem na řešení a vyberte **obnovení balíčků NuGet**) před povolením testování částí životností.


## <a name="does-live-unit-testing-work-with-net-core"></a>Live testování částí funguje s .NET Core?

**Odpověď:**

Ano. Za provozu testování částí funguje s .NET Core a rozhraní .NET Framework. Ve Visual Studio 2017 verze 15.3 byla nedávno přidána podpora pro .NET Core. Proveďte upgrade na tuto verzi sady Visual Studio, pokud chcete, podpora živé testování částí pro .NET Core.

## <a name="why-doesnt-live-unit-testing-work-when-i-turn-it-on"></a>Proč Live testování částí nefunguje, pokud zapnutím?

**Odpověď:**

**Výstup – okno** (Pokud je vybrán Live testování částí rozevíracího seznamu) by měl zjistit, proč Live jednotkové testování není funkční. Testování částí za provozu, nemusí fungovat pro jednu z následujících důvodů:

- Pokud se balíčky NuGet odkazuje projekty v řešení nebyly obnoveny, Live testování částí nebude fungovat. To explicitní sestavení řešení nebo při obnovování balíčků NuGet v řešení před zapnutím Live testování částí v by měl tento problém vyřešit.

- Pokud používáte na základě Mstestu testů ve svých projektech, ujistěte se, že odeberte odkaz na `Microsoft.VisualStudio.QualityTools.UnitTestFramework`a přidejte odkazy na nejnovější balíčky NuGet Mstestu, `MSTest.TestAdapter` (je vyžadována minimální verzi 1.1.11) a `MSTest.TestFramework` (minimální verze 1.1.11 je vyžadována). Další informace najdete v části "Systémů podporované testování" [použití Live jednotkové testování v aplikaci Visual Studio 2017 Enterprise Edition](live-unit-testing.md#supported-test-frameworks) tématu.

- Alespoň jeden projekt ve vašem řešení by měl mít buď NuGet odkaz, nebo přímý odkaz na xUnit, NUnit nebo Mstestu test framework. Tento projekt by měl odkazovat také odpovídající balíček NuGet sady Visual Studio test adaptéry. Adaptér testovací sady Visual Studio lze také odkazovat prostřednictvím `.runsettings` souboru. `.runsettings` Soubor musí mít položka podobná té následující:

   ```xml
    <RunSettings>
       <RunConfiguration>
          <TestAdaptersPaths>path-to-your-test-adapter</TestAdaptersPaths>
       </RunConfiguration>
    </RunSettings>
   ``` 

## <a name="why-does-live-unit-testing-show-incorrect-coverage-after-you-upgrade-the-test-adapter-referenced-in-your-visual-studio-projects-to-the-supported-version"></a>Proč Live testování částí zobrazuje nesprávné pokrytí po upgradu testovací adaptér odkazovaný ve vašem projektů sady Visual Studio podporovanou verzi?

**Odpověď:**

- Pokud více projektů současně odkaz na řešení NuGet otestovat adaptér balíčku, každý z nich je nutné upgradovat na podporovanou verzi.

- Zajistěte, aby soubor PROPS MSBuild importovat z balíčku adaptér testovací správně aktualizovat také. Kontrola NuGet balíček verze či cestu importu, které lze obvykle zjistit v horní části souboru projektu, podobně jako tento:

   ```xml
    <Import Project="..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props" Condition="Exists('..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props')" />
   ```

## <a name="can-i-customize-my-live-unit-testing-builds"></a>Můžete přizpůsobit Moje Live testování částí sestavení?

**Odpověď:**

Pokud vaše řešení vyžaduje vlastní postup pro sestavení pro instrumentace (Live jednotkové testování), které nejsou nutné pro "Regulérní"-instrumentovány sestavení, pak můžete přidat kód pro váš projekt nebo .targets soubory, které vyhledává `BuildingForLiveUnitTesting` vlastnost a provede kroky sestavení vlastní předzálohovacího nebo pozálohovacího. Můžete také odebrat určité kroky sestavení (třeba publikování nebo generování balíčky) nebo přidat kroky sestavení (jako je například kopírování požadavky) do Live testování částí sestavení na základě této vlastnosti projektu. To nijak nezmění regulární buildu jakýmkoli způsobem a ovlivní pouze za provozu testování částí sestavení.

Například může být na cíl, který vytváří balíčků NuGet při pravidelné vytváření sestavení. Pravděpodobně nechcete balíčky NuGet, které má být vygenerován po každé úpravy, které provedete. Proto můžete zakázat tento cíl v za provozu jednotkové testování sestavení pomocí tohoto postupu přibližně takto:  

```xml
<Target Name="GenerateNuGetPackages" BeforeTargets="AfterBuild" Condition="'$(BuildingForLiveUnitTesting)' != 'true'">
    <Exec Command='"$(MSBuildThisFileDirectory)..\tools\GenPac" '/>
</Target>
```

## <a name="error-messages-with-ltoutputpathgt-or-ltoutdirgt"></a>Chybové zprávy s &lt;OutputPath&gt; nebo &lt;OutDir&gt;

**Proč se při Live testování částí se pokusí vytvořit mém řešení zobrazí následující chyba: ".. .se objeví bezpodmínečně nastavit `<OutputPath>` nebo `<OutDir>`. Za provozu testování částí nebude provést testy z výstupu sestavení"?**

**Odpověď:**

K tomu může dojít, pokud proces sestavení pro vaše řešení bezpodmínečně přepsání `<OutputPath>` nebo `<OutDir>` tak, aby se nejedná o podadresář `<BaseOutputPath>`. V takových případech Live testování částí nebude fungovat, protože tyto zajistit, že jsou vyřadit artefaktů sestavení do složky v Potlačí také `<BaseOutputPath>`. Pokud je nutné přepsat umístění, kde chcete sestavení artefaktů vyřadit v pravidelných sestavení, přepsat `<OutputPath>` podmíněně na základě `<BaseOutputPath>`.

Například, pokud přepsání buildu `<OutputPath>` jak je uvedeno níže:

```xml 
<Project>
  <PropertyGroup>
    <OutputPath>$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)</OutputPath>
  </PropertyGroup>
</Project>
```

potom můžete nahradit s následujícími službami:

```xml 
<Project>
  <PropertyGroup>
    <BaseOutputPath Condition="'$(BaseOutputPath)' == ''">$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)\</BaseOutputPath>
    <OutputPath Condition="'$(OutputPath)' == ''">$(BaseOutputPath)</OutputPath>
  </PropertyGroup>
</Project>
```
 
To zajistí, že `<OutputPath>` spočívá v rámci `<BaseOutputPath>` složky.

Nelze přepsat `<OutDir>` přímo v procesu sestavení; přepsání `<OutputPath>` místo toho chcete-li vyřadit artefaktů sestavení do určitého umístění.
 
## <a name="setting-the-location-of-live-unit-testing-build-artifacts"></a>Nastavení umístění sestavení artefaktů Live testování částí

**Chci, aby artefakty sestavení Live testování částí přejdete do určitého umístění místo výchozí umístění v rámci `.vs` složky. Jak můžete změnit který?**

**Odpověď:**

Nastavte `LiveUnitTesting_BuildRoot` proměnnou prostředí individuální na cestu, kde chcete Live jednotky testování sestavení artefaktů chcete vyřadit. 

## <a name="how-is-running-tests-from-test-explorer-window-different-from-running-tests-in-live-unit-testing"></a>Jak je spouštění testů z okna Průzkumníka testů liší od spuštění testů v za provozu jednotkové testování?

**Odpověď:**

Existuje několik rozdílů:

- Spuštěna nebo k ladění testy z okna Průzkumníka testů spustí regulární binární soubory, zatímco Live testování částí spouští instrumentované binární soubory. Pokud chcete ladit instrumentované binární soubory, přidávání [Debugger.Launch](xref:System.Diagnostics.Debugger.Launch) volání metody ve své metodě testovací způsobí, že ladicí program ke spuštění vždy, když metoda spuštěna (včetně když je proveden za provozu testování částí), a pak můžete Připojte a ladění instrumentované binární. Naše naděje je však instrumentace je transparentní pro vás pro většinu scénářů uživatele, a že není potřeba ladění instrumentovány binární soubory.

- Za provozu jednotkové testování nevytvoří nové domény aplikace ke spuštění testů, ale testy spustit z okna Průzkumníka testů vytvořit novou doménu aplikace.

- Za provozu jednotkové testování spustí testy v každém testu sestavení postupně, že pokud spouštíte více testů z okna Průzkumníka testů a jste vybrali **spuštění testů paralelně** tlačítko poběží v paralelně.

- Zjišťování a provádění testů v za provozu testování částí používá verze 2 `TestPlatform`, zatímco okno Průzkumníka testů používá verze 1. Rozdíl ve většině případů by neměl ale Všimněte si. 

- Průzkumníka testů aktuálně spustí testy v single-threaded apartment (STA) ve výchozím nastavení, zatímco Live testování částí spustí testy v více vláken typu apartment (MTA). V STA v za provozu jednotkové testování spustit Mstestu testů, uspořádání metodu testovací nebo třídě obsahující s `<STATestMethod>` nebo `<STATestClass>` atribut, který se nachází v `MSTest.STAExtensions 1.0.3-beta` balíček NuGet. Pro NUnit, uspořádání testů metoda s `<RequiresThread(ApartmentState.STA)>` atributů a pro xUnit, s `<STAFact>` atribut.

## <a name="how-do-i-exclude-tests-from-participating-in-live-unit-testing"></a>Jak vyloučit testy ze za provozu jednotkové testování?

**Odpověď:**

Najdete v části "zahrnutí a vyloučení testování projektů a testování metod" [použití Live jednotkové testování v aplikaci Visual Studio 2017 Enterprise Edition](live-unit-testing.md#including-and-excluding-test-projects-and-test-methods) téma pro uživatelská nastavení. To je velmi užitečné, když chcete spustit konkrétní sadu testů pro relaci úpravy konkrétní nebo zachovat vlastní osobní preference.
 
Pro nastavení pro konkrétní řešení, můžete použít <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute?displayProperty=fullName> atribut prostřednictvím kódu programu pro vyloučení metody, vlastnosti, třídy a struktury z se instrumentovány Live testování jednotky. Kromě toho můžete také nastavit `<ExcludeFromCodeCoverage>` vlastnost `true` v souboru projektu z se instrumentovány vyloučit celý projekt. Za provozu testování částí bude i nadále spustit testy, které nebyly byla instrumentována, ale nebude vizualizovat jejich pokrytí.

Můžete také zkontrolovat, zda `Microsoft.CodeAnalysis.LiveUnitTesting.Runtime` v aktuální doméně aplikace, zakázat testy, podle které. Například můžete provést něco podobného jako na následujícím obrázku se xUnit:

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

## <a name="why-are-win32-pe-headers-different-in-instrumented-assemblies-built-by-live-unit-testing"></a>Proč se liší v instrumentovaného sestavení vytvořené za provozu jednotkové testování záhlaví Win32 PE?

**Odpověď:**

Tento problém vyřešen a v neexistuje ve Visual Studio 2017 verze 15.3. Proveďte upgrade na tuto verzi sady Visual Studio.

Pro starší verze aplikace Visual Studio 2017 je známého problému, který může mít za následek Live testování částí sestavení chybě pro vložení následující data záhlaví PE Win32:

- Verze souboru (zadáno v @System.Reflection.AssemblyFileVersionAttribute v kódu).

- Ikona Win32 (zadáno v `/win32icon:` na příkazovém řádku).

- Win32 Manifest (zadáno v `/win32manifest:` na příkazovém řádku).

Testy, které jsou závislé na tyto hodnoty může selhat, při spuštění testování částí za provozu.

## <a name="why-does-live-unit-testing-keep-building-my-solution-all-the-time-even-if-i-am-not-making-any-edits"></a>Proč testování zachovat vytváření mém řešení vždy, i v případě, že není možné provedení veškeré úpravy částí za provozu?

**Odpověď:**

K tomu může dojít, pokud proces vytváření vašeho řešení generuje zdrojový kód, který je součástí řešení sám a vaše soubory cíl sestavení nemají odpovídající vstupy a výstupy zadaný. Cíle by měly mít seznam vstupy a výstupy, aby mohli provést odpovídající aktuální kontroly a určit, zda je požadovaný nového sestavení nástroje MSBuild.

Testování částí za provozu spustí sestavení vždy, když zjistí, že došlo ke změně zdrojových souborů. Protože sestavení řešení generuje zdrojové soubory, Live testování částí dostane do sestavení nekonečné smyčky. Pokud však vstupy a výstupy cíle jsou zaškrtnutá políčka při Live jednotkové testování spuštění druhého sestavení (po zjišťování nově vytvořených zdrojových souborů z předchozího sestavení), protože kontroly vstupy a výstupy označí, ji budou rozdělit mimo smyčku jestli všechno, co je aktuální.  

## <a name="how-does-live-unit-testing-work-with-the-lightweight-solution-load-feature"></a>Jak funguje práci s funkcí Lightweight řešení zatížení testování částí za provozu?

**Odpověď:**

Testování částí za provozu není aktuálně fungují dobře u zatížení funkci lightweight řešení. Funguje pouze po nejméně jedna z projektů testování načtení. Do té doby nebudou fungovat, protože za provozu testování částí je závislá na alespoň jeden z projektů testování odkazující na testovací adaptér (Mstestu, xUnit nebo NUnit) načítá.

> [!NOTE]
> Prosté řešení zatížení již není k dispozici ve verzi Visual Studio 2017 15,5 a novějším. V aplikaci Visual Studio 2017 verze 15,5 a novější velkých řešení, které obsahují spravované kód zatížení mnohem rychleji než dřív, i bez zatížení lightweight řešení.

## <a name="why-does-live-unit-testing-does-not-capture-coverage-from-a-new-process-created-by-a-test"></a>Proč Live testování částí nezachytává pokrytí z nový proces vytvořené testu?

**Odpověď:**

Jedná se o známý problém, nutné opravit v další aktualizaci sady Visual Studio 2017.

## <a name="why-does-nothing-happen-after-i-include-or-exclude-tests-from-the-live-test-set"></a>Proč nic stát po můžu zahrnout nebo vyloučit testů ze sady testů za provozu?

**Odpověď:**

Tento problém vyřešen a v aplikaci Visual Studio 2017 verze 15.3 neexistuje. Upgrade na tuto verzi sady Visual Studio.

Pro starší verze aplikace Visual Studio 2017 jedná se o známý problém. Chcete-li tento problém obejít, bude třeba, aby upravíte na libovolný soubor po zahrnout nebo vyloučit testy. 

## <a name="live-unit-testing-and-editor-icons"></a>Testování částí a editor ikony za provozu

**Proč nevidím žádné ikony v editoru Přestože Live testování částí zdá se, že se spuštěním testů na základě zpráv v okně výstupu?**

**Odpověď:**

K tomu dojde, pokud z nějakého důvodu nejsou instrumentovány sestavení, která Live testování částí pracuje na. Například není kompatibilní s projekty, které nastavit Live testování částí `<UseHostCompilerIfAvailable>false</UseHostCompilerIfAvailable>`. V takovém případě je třeba aktualizovat buď odeberte toto nastavení, nebo změňte ho na vaše procesu sestavení `true` pro Live testování částí pro práci. 

## <a name="how-do-i-collect-more-detailed-logs-to-file-bug-reports"></a>Jak můžu shromáždit protokoly podrobnější souborů sestav chyb?

**Odpověď:**

Můžete provést shromážděte podrobnější protokoly na několik věcí:

- Přejděte na **nástroje**, **možnosti**, **Live testování částí** a změňte možnost protokolování **podrobné**. To způsobí, že podrobnější protokoly zobrazený v okně výstupu.

- Nastavte `LiveUnitTesting_BuildLog` uživatelské proměnné prostředí k názvu souboru, kterou chcete použít k zachycení MSBuild protokolu. Podrobné zprávy protokolu nástroje MSBuild ze za provozu testování částí sestavení může načíst pak z tohoto souboru.

- Nastavte `LiveUnitTesting_TestPlatformLog` uživatelské proměnné prostředí pro `1` k zachycení protokolu testovací platformy. Podrobné zprávy protokolu platformy testu z Live testování částí spustí lze poté načíst z `[Solution Root]\.vs\[Solution Name]\log\[VisualStudio Process ID]`.

- Vytvoření prostředí individuální proměnné s názvem `VS_UTE_DIAGNOSTICS` a nastavte ji na hodnotu 1 (nebo libovolná hodnota) a restartujte Visual Studio. Teď byste měli vidět spoustu protokolování v **výstup - testy** kartě v sadě Visual Studio.

## <a name="see-also"></a>Viz také

[Živé testování částí](live-unit-testing.md)

