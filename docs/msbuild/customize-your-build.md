---
title: Přizpůsobení sestavení | Dokumentace Microsoftu
ms.date: 06/13/2019
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8e644fd6fc521318512bbc5dd25838a379af78a9
ms.sourcegitcommit: dd3c8cbf56c7d7f82f6d8818211d45847ab3fcfc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141160"
---
# <a name="customize-your-build"></a>Přizpůsobení sestavení

Projekty MSBuild, které používají standardní proces sestavení (import *Microsoft.Common.props* a *cílů Microsoft.Common.targets*) mají několik háky rozšíření, které můžete použít k přizpůsobení sestavení proces.

## <a name="add-arguments-to-command-line-msbuild-invocations-for-your-project"></a>Přidání argumentů příkazového řádku MSBuild volání pro váš projekt

A *Directory.Build.rsp* souboru nebo nad zdrojový adresář se použijí pro sestavení příkazového řádku vašeho projektu. Podrobnosti najdete v tématu [soubory odezvy nástroje MSBuild](../msbuild/msbuild-response-files.md#directorybuildrsp).

## <a name="directorybuildprops-and-directorybuildtargets"></a>Directory.Build.props a Directory.Build.targets

Před MSBuild verze 15 Pokud byste chtěli poskytnout nových, vlastních vlastností do projektů ve vašem řešení, museli jste ručně přidejte odkaz na tuto vlastnost pro každý soubor projektu v řešení. Nebo jste museli definovat vlastnost *.props* souboru a k následnému importování explicitně *.props* soubor ve všech projektech v řešení, mimo jiné.

Ale nyní můžete přidat nové vlastnosti pro každý projekt v jednom kroku definováním v jednotlivých souborů volané *Directory.Build.props* v kořenové složce, která obsahuje váš zdroj. Při spuštění nástroje MSBuild *Microsoft.Common.props* vyhledá strukturu pro *Directory.Build.props* souboru (a *cílů Microsoft.Common.targets* hledá *Directory.Build.targets*). Pokud jeden najde, importuje vlastnost. *Directory.Build.props* je uživatelem definovaného souboru, který obsahuje vlastní nastavení pro projekty v adresáři.

> [!NOTE]
> Systémy založené na Linuxu souborů jsou malá a velká písmena. Ujistěte se, že použití malých a velkých Directory.Build.props název souboru odpovídá přesně nebo ho nerozpozná během procesu sestavení.
>
> Zobrazit [tento problém Githubu](https://github.com/dotnet/core/issues/1991#issue-368441031) Další informace.

### <a name="directorybuildprops-example"></a>Příklad Directory.Build.props

Například Kdybyste chtěli povolit všechny projekty pro přístup k nového Roslynu **/ deterministic** funkci (což je zpřístupněná platformě Roslyn `CoreCompile` cílové vlastností `$(Deterministic)`), udělat následující.

1. Vytvořte nový soubor v kořenové složce úložiště volána *Directory.Build.props*.
2. Přidejte následující kód XML do souboru.

   ```xml
   <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
   </Project>
   ```

3. Run MSBuild. Váš projekt importů existující *Microsoft.Common.props* a *cílů Microsoft.Common.targets* najít soubor a naimportujte ho.

### <a name="search-scope"></a>Obor vyhledávání

Při hledání *Directory.Build.props* adresářovou strukturu souboru, MSBuild nahoru vás z umístění vašeho projektu (`$(MSBuildProjectFullPath)`), zastavování po je možné vyhledat *Directory.Build.props* soubor. Například pokud vaše `$(MSBuildProjectFullPath)` byl *c:\users\username\code\test\case1*, MSBuild bude zahájeno hledání existuje a pak vyhledejte adresářovou strukturu směrem nahoru, dokud se nachází *Directory.Build.props* soubor jako v následující adresářovou strukturu.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```

Umístění souboru řešení je závislé na *Directory.Build.props*.

### <a name="import-order"></a>Importovat pořadí

*Directory.Build.props* velmi brzy importu v *Microsoft.Common.props*, a nejsou k dispozici pro jeho vlastnosti definované později. Vyhněte se proto odkazující na vlastnosti, které nejsou ještě definovány (a bude vyhodnocena jako prázdná).

*Directory.Build.targets* je importován z *cílů Microsoft.Common.targets* po importu *.targets* soubory z balíčků NuGet. Tedy můžete přepsat vlastnosti a cíle definované ve většině logiku sestavení, ale někdy možná muset upravit soubor projektu po posledním importu.

### <a name="use-case-multi-level-merging"></a>Případ použití: víceúrovňové sloučení

Předpokládejme, že máte tato struktura standardní řešení:

```
\
  MySolution.sln
  Directory.Build.props     (1)
  \src
    Directory.Build.props   (2-src)
    \Project1
    \Project2
  \test
    Directory.Build.props   (2-test)
    \Project1Tests
    \Project2Tests
```

Může být žádoucí použít společná nastavení pro všechny projekty *(1)* , společná nastavení pro *src* projekty *(2 src)* a běžné vlastnosti  *testování* projekty *(2-test)* .

Aby MSBuild správně sloučit "vnitřní" soubory (*2 src* a *2 test*) s "vnější" souboru (*1*), musí vzít v úvahu, že jakmile MSBuild najde *Directory.Build.props* souboru, zastaví další kontrolu. Pokud chcete pokračovat, kontrolu a sloučení do vnějšího souboru, vložte tento kód do obou vnitřní souborů:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

Přehled nástroje MSBuild pro obecný postup je následující:

- U každého projektu, MSBuild najde první *Directory.Build.props* směrem nahoru ve struktuře řešení sloučí s výchozím nastavením a zastaví skenování Další informace
- Pokud chcete najít a pak sloučit několik úrovní [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (popsaný výš) "vnější" soubor ze souboru "vnitřní"
- Pokud "vnější" soubor nemá sama také importovat něco nad ním, pak prohledávání zastaví existuje
- Chcete-li řízení procesu skenování/sloučení, použijte `$(DirectoryBuildPropsPath)` a `$(ImportDirectoryBuildProps)`

Nebo jednoduše: první *Directory.Build.props* , který není nic importu je, kde zastaví MSBuild.

### <a name="choose-between-adding-properties-to-a-props-or-targets-file"></a>Výběr mezi přidání vlastností do souboru props nebo .targets

Nástroj MSBuild je závislé na import pořadí a poslední definice vlastnosti (nebo `UsingTask` nebo cíl) je definice použitá.

Při použití explicitní importy, můžete importovat z *.props* nebo *.targets* soubor v libovolném bodě. Tady je často používaný konvence:

- *.props* importu souborů v rané fázi importu pořadí.

- *.TARGETS* soubory jsou importovány v pořadí sestavení.

Tato konvence je vynucena `<Project Sdk="SdkName">` importuje (to znamená, import *Sdk.props* nastane dřív, než celý obsah souboru, pak *Sdk.targets* obsahuje poslední, až potom obsah Soubor).

Při rozhodování, kam chcete vložit vlastnosti, použijte následující obecné pokyny:

- Pro mnoho vlastností nezáleží, ve které jsou definovány, protože se nepřepíšou a pouze v době spuštění se budou číst.

- Pro chování, které může přizpůsobit v jednotlivých projektů, nastavit výchozí hodnoty *.props* soubory.

- Vyhněte se nastavování závislé vlastnosti *.props* soubory načtením hodnota může být vlastní vlastnosti, protože vlastní nastavení se neprovede, dokud nástroj MSBuild načítá projektu daného uživatele.

- Nastavte závislé vlastnosti *.targets* soubory, protože budete vyzvednutí vlastní nastavení z jednotlivých projektů.

- Pokud je potřeba přepsat vlastnosti, provést *.targets* souboru po všechna vlastní nastavení uživatele a project jste využili příležitost dobře se projeví. Buďte opatrní při použití odvozených vlastnosti; odvozené vlastnosti může být potřeba také přepsat.

- Zahrnout položky v *.props* soubory (záleží na vlastnost). Všechny vlastnosti jsou považovány za před jakoukoli položku, tak, aby uživatel projektu vlastnost přizpůsobení získat neexistoval, a to projektu daného uživatele dává příležitost `Remove` nebo `Update` libovolnou položku získaných importu.

- Definování cílů v *.targets* soubory. Nicméně pokud *.targets* importovaných souborů pomocí sady SDK, mějte na paměti, že tento scénář umožňuje přepsání cíl obtížnější, protože uživatele projekt nemá místo, kde můžete přepsat ve výchozím nastavení.

- Pokud je to možné preferovat úpravy vlastností v době vyhodnocení přes změna vlastností v cíli. Toto pravidlo je snazší načtení projektu a pochopit, co dělají.

## <a name="msbuildprojectextensionspath"></a>MSBuildProjectExtensionsPath

Ve výchozím nastavení *Microsoft.Common.props* importuje `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.props` a *cílů Microsoft.Common.targets* importuje `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.targets`. Výchozí hodnota `MSBuildProjectExtensionsPath` je `$(BaseIntermediateOutputPath)`, `obj/`. NuGet používá tento mechanismus pro odkazování na sestavení logiky dodávají s balíčky; To znamená, vytvoří v době obnovení `{project}.nuget.g.props` soubory, které odkazují na obsah balíčku.

Tento mechanismus rozšíření můžete zakázat nastavením vlastnosti `ImportProjectExtensionProps` k `false` v *Directory.Build.props* nebo před importem *Microsoft.Common.props*.

> [!NOTE]
> Zakázání MSBuildProjectExtensionsPath importy zabrání logiku sestavení poskytované v balíčcích NuGet použití do projektu. Některé balíčky NuGet vyžadovat sestavení logiku pro svou funkci provést a zobrazí se zbytečné když je tato možnost zakázána.

## <a name="user-file"></a>soubor .user

*Microsoft.Common.CurrentVersion.targets* importuje `$(MSBuildProjectFullPath).user` pokud existuje, takže si můžete vytvořit soubor vedle svého projektu pomocí rozšíření, další. Pro dlouhodobé změny, které máte v plánu vrácení se změnami do správy zdrojového kódu dáváte přednost projektu se mění, aby budoucí programu nemusíte vědět o tento mechanismus rozšíření.

## <a name="msbuildextensionspath-and-msbuilduserextensionspath"></a>MSBuildExtensionsPath and MSBuildUserExtensionsPath

> [!WARNING]
> Pomocí těchto mechanismů rozšíření učiní obtížnější získat opakovatelných sestavení napříč počítači. Zkuste použít konfigurace, která může být zapsány do systému správy zdrojů a sdílí všichni vývojáři vašeho základu kódu.

Podle konvence mnoho základních import souborů logiku sestavení

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportBefore\*.targets
```

před jejich obsah a

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportAfter\*.targets
```

později. Tato konvence umožňuje nainstalovaných sad SDK k posílení logiku sestavení běžných typů projektu.

Stejnou adresářovou strukturu je prohledávána v `$(MSBuildUserExtensionsPath)`, což je složka uživatelská *%LOCALAPPDATA%\Microsoft\MSBuild*. Pro všechna sestavení odpovídající typ projektu spuštěné pod přihlašovacími údaji uživatele se naimportují soubory umístěné v této složce. Rozšíření uživatele můžete zakázat nastavením vlastnosti s názvem po importu souboru ve vzoru `ImportUserLocationsByWildcardBefore{ImportingFileNameWithNoDots}`. Například nastavení `ImportUserLocationsByWildcardBeforeMicrosoftCommonProps` k `false` by jinak znemožňovaly import `$(MSBuildUserExtensionsPath)\$(MSBuildToolsVersion)\Imports\Microsoft.Common.props\ImportBefore\*`.

## <a name="customize-the-solution-build"></a>Přizpůsobení sestavení řešení

> [!IMPORTANT]
> Přizpůsobení sestavení řešení tímto způsobem se vztahuje pouze na příkazový řádek sestavení s *MSBuild.exe*. To **nemá** platí pro sestavení v sadě Visual Studio.

Když MSBuild vytvoří soubor řešení, nejprve ji interně překládá do souboru projektu a pak sestavení se stavem. Importuje soubor generovaný projekt `before.{solutionname}.sln.targets` před definováním veškerých cílů a `after.{solutionname}.sln.targets` po importu cílů včetně cílů nainstalovaná `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportBefore` a `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportAfter` adresáře.

Například můžete definovat nový cíl k zápisu zprávy do vlastního protokolu po sestavení *MyCustomizedSolution.sln* vytvořením souboru ve stejném adresáři s názvem *po. MyCustomizedSolution.sln.targets* , který obsahuje

```xml
<Project>
 <Target Name="EmitCustomMessage" AfterTargets="Build">
   <Message Importance="High" Text="The solution has completed the Build target" />
 </Target>
</Project>
```

## <a name="see-also"></a>Viz také:

- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)

- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
