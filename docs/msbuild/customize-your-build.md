---
title: Přizpůsobení buildu | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5ea021decfc0940ecaaedde2ecfdde34db833b86
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="customize-your-build"></a>Přizpůsobení buildu

Proces sestavení projektů MSBuild, které používají standardní (import `Microsoft.Common.props` a `Microsoft.Common.targets`) mají několik háky rozšiřitelnosti, které lze použít k přizpůsobení procesu sestavení.

## <a name="adding-arguments-to-command-line-msbuild-invocations-for-your-project"></a>Přidání argumenty příkazového řádku nástroje MSBuild volání pro svůj projekt

A `Directory.Build.rsp` souboru nebo nad zdrojový adresář se použijí pro sestavení příkazového řádku projektu. Podrobnosti najdete v tématu [soubory odezvy nástroje MSBuild](../msbuild/msbuild-response-files.md#directorybuildrsp).

## <a name="directorybuildprops-and-directorybuildtargets"></a>Directory.Build.props a Directory.Build.targets

Ve verzích nástroje MSBuild starší než verze 15 Pokud chcete zadat novou, vlastní vlastnost, která má projekty v řešení, museli jste ručně přidejte odkaz na tuto vlastnost pro každý soubor projektu v řešení. Nebo, jste měli k definování vlastností v *props* souboru a pak můžete importovat explicitně *props* souboru v všechny projekty v řešení, mimo jiné.

Ale nyní můžete přidat novou vlastnost na všechny projekty v jednom kroku definováním v jednoho souboru s názvem *Directory.Build.props* v kořenové složce, která obsahuje vaše zdroj. Při spuštění nástroje MSBuild *Microsoft.Common.props* vyhledá struktury adresářů pro *Directory.Build.props* souboru (a *Microsoft.Common.targets* hledá *Directory.Build.targets*). V případě, že některou najde, naimportuje vlastnost. *Directory.Build.props* je soubor definovaný uživatelem, který poskytuje přizpůsobení projektů adresáře.

### <a name="directorybuildprops-example"></a>Příklad Directory.Build.props

Například, pokud chcete povolit všechny projekty pro přístup k nové Roslyn **/ deterministickou** funkce (což je zpřístupněná Roslyn `CoreCompile` cíl vlastností `$(Deterministic)`), můžete to udělat následující.

1. Vytvořte nový soubor v kořenovém vašeho úložiště volána *Directory.Build.props*.
2. Přidejte následující kód XML do souboru.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. Spuštění nástroje MSBuild. Importuje existující vašeho projektu z *Microsoft.Common.props* a *Microsoft.Common.targets* najít soubor a importujte ho.

### <a name="search-scope"></a>Obor vyhledávání

Při hledání *Directory.Build.props* adresářové struktury souboru MSBuild směrem nahoru provede z umístění vašeho projektu (`$(MSBuildProjectFullPath)`), zastavování po je možné vyhledat *Directory.Build.props* soubor. Například pokud vaše `$(MSBuildProjectFullPath)` byla *c:\users\username\code\test\case1*MSBuild by spusťte hledání existuje a pak hledání strukturu adresáře směrem nahoru, dokud se nachází *Directory.Build.props* souboru, jako následující adresářovou strukturu.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```

Umístění souboru řešení není závislé na *Directory.Build.props*.

### <a name="import-order"></a>Import pořadí

*Directory.Build.props* je velmi brzy v naimportována *Microsoft.Common.props*, takže vlastnosti definované později nejsou k dispozici na ni. Ano Vyhněte se odkazující na vlastnosti, které ještě nejsou definovány (a tedy vyhodnotí jako prázdný).

*Directory.Build.targets* je naimportovaná ze *Microsoft.Common.targets* po importu *.targets* soubory z balíčků NuGet. Ano může sloužit k přepsání vlastnosti a definované ve většině logiky sestavení cílů, ale v některých případech může být nutné udělat úpravy v souboru projektu po posledním importu.

### <a name="use-case-multi-level-merging"></a>Případ použití: víceúrovňovou sloučení

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

Může být žádoucí, aby společných vlastností pro všechny projekty *(1)*, společných vlastností pro *src* projekty *(2-src)* a společných vlastností pro  *testování* projekty *(2-test)*.

Pro MSBuild správně sloučit "vnitřní" soubory (*2 src* a *2-test*) "vnější" souborem (*1*), je třeba vzít v úvahu, že jednou MSBuild vyhledá *Directory.Build.props* souboru, zastaví další kontrolu. Pokud chcete pokračovat, kontrolu a sloučení do vnějšího souboru, umístěte do obou vnitřní soubory toto:

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

Souhrn MSBuild je obecný přístup je následující:

- Pro daný projekt, MSBuild vyhledá první *Directory.Build.props* směrem nahoru ve struktuře řešení sloučí s výchozím nastavením a zastaví kontrolu Další informace
- Pokud chcete, aby více úrovní najít a pak sloučit [ `<Import...>` ](../msbuild/property-functions.md#msbuild-getpathoffileabove) (viz výše) "vnější" soubor ze souboru "vnitřní"
- Pokud soubor "vnější" nemá sám také importovat něco nad ním, pak kontrolu zastaví existuje
- Chcete-li řídit proces kontrolu sloučení, použijte `$(DirectoryBuildPropsPath)` a `$(ImportDirectoryBuildProps)`

Nebo jednodušeji: první *Directory.Build.props* který neimportuje nic, je, kde MSBuild zastaví.

## <a name="msbuildprojectextensionspath"></a>MSBuildProjectExtensionsPath

Ve výchozím nastavení `Microsoft.Common.props` importuje `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.props` a `Microsoft.Common.targets` importuje `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.targets`. Výchozí hodnota `MSBuildProjectExtensionsPath` je `$(BaseIntermediateOutputPath)`, `obj/`. Toto je mechanismus, který NuGet používá k odkazování na sestavení logiku doručit s balíčky, to znamená, vytvoří v době obnovení `{project}.nuget.g.props` soubory, které odkazují na obsah balíčku.

Tento mechanismus rozšiřitelnosti lze zakázat pomocí nastavení vlastnosti `ImportProjectExtensionProps` k `false` v `Directory.Build.props` nebo před importem `Microsoft.Common.props`.

> [!NOTE]
> Vypnutí MSBuildProjectExtensionsPath importy zabrání sestavení logiku doručit do balíčků NuGet od použití do projektu. Některé balíčky NuGet vyžadují sestavení logiku pro provádění jejich funkce a bude vykreslen nemá, když to je zakázáno.

## <a name="user-file"></a>.uživatel souboru

Importuje Microsoft.Common.CurrentVersion.targets `$(MSBuildProjectFullPath).user` pokud existuje, takže si můžete vytvořit soubor vedle váš projekt pomocí další rozšíření. Pro dlouhodobou změny, které máte v plánu vrácení se změnami do správy zdrojového kódu dáváte přednost změna projektu a tak, aby budoucí údržby programu nemusíte vědět o tento mechanismus rozšíření.

## <a name="msbuildextensionspath-and-msbuilduserextensionspath"></a>MSBuildExtensionsPath a MSBuildUserExtensionsPath

> [!WARNING]
> Pomocí těchto mechanismů rozšíření znesnadňuje získat opakovatelných sestavení mezi počítači. Zkuste použít konfigurace, které je možné zkontrolovat do systému správy zdrojů a sdílí všechny vývojáři vaší základu kódu.

Podle konvence pro mnoho základní import souborů logiky sestavení

```
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportBefore\*.targets
```

před jejich obsah a

```
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportAfter\*.targets
```

potom. To umožňuje nainstalované sady SDK k posílení sestavení logiku běžné typy projektů.

Prohledají se stejného adresářové struktury v `$(MSBuildUserExtensionsPath)`, což je uživatelská složka `%LOCALAPPDATA%\Microsoft\MSBuild`. Soubory, které jsou umístěny v této složce budou naimportovány pro všechny sestavení odpovídající typ projektu spuštěná s pověřeními uživatele. Rozšíření uživatele lze zakázat pomocí nastavení vlastností s názvem po importu souboru ve vzoru `ImportUserLocationsByWildcardBefore{ImportingFileNameWithNoDots}`. Například nastavení `ImportUserLocationsByWildcardBeforeMicrosoftCommonProps` k `false` by jinak znemožňovaly import `$(MSBuildUserExtensionsPath)\$(MSBuildToolsVersion)\Imports\Microsoft.Common.props\ImportBefore\*`.

## <a name="customizing-the-solution-build"></a>Přizpůsobení sestavení řešení

> [!IMPORTANT]
> Přizpůsobení sestavení řešení tímto způsobem se vztahuje pouze na příkazového řádku sestavení s `MSBuild.exe`. Ho **nemá** použít k sestavení v sadě Visual Studio.

Při MSBuild sestavení soubor řešení, nejdřív ho interně překládá do souboru projektu a pak sestavení, která. Importuje soubor generovaný projektu `before.{solutionname}.sln.targets` před definováním veškerých cílů a `after.{solutionname}.sln.targets` po importu cíle, včetně cílů nainstalována do `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportBefore` a `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportAfter` adresáře.

Můžete například definovat nový cíl pro zápis zprávy vlastní protokol po sestavení `MyCustomizedSolution.sln` pomocí souboru ve stejném adresáři s názvem `after.MyCustomizedSolution.sln.targets` obsahující

```xml
<Project>
 <Target Name="EmitCustomMessage" AfterTargets="Build">
   <Message Importance="High" Text="The solution has completed the Build target" />
 </Target>
</Project>
```

## <a name="see-also"></a>Viz také

 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md) [MSBuild – Reference](../msbuild/msbuild-reference.md)
