---
title: "Návod: Použití nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, tutorial
ms.assetid: b8a8b866-bb07-4abf-b9ec-0b40d281c310
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: de0e5fe3d00f4f641fb2e7e28cae7802c32822de
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="walkthrough-using-msbuild"></a>Návod: Použití nástroje MSBuild
MSBuild je platforma sestavení pro Microsoft a Visual Studio. Tento návod vás seznámí s stavební bloky nástroje MSBuild a ukazuje, jak k zápisu, manipulaci a ladění projektů MSBuild. Co se dozvíte o:

-   Vytváření a manipulace s nimi souboru projektu.

-   Použití vlastností sestavení

-   Jak používat sestavení položky.

 Spuštěním nástroje MSBuild ze sady Visual Studio nebo pomocí příkazového okna. V tomto návodu vytvoříte soubor projektu nástroje MSBuild pomocí sady Visual Studio. Upravte soubor projektu v sadě Visual Studio a použít okno příkazového řádku pro sestavení projektu a podívejte se na výsledky.

## <a name="creating-an-msbuild-project"></a>Vytvoření projektu nástroje MSBuild
 Systém projektu sady Visual Studio je založen na MSBuild. To usnadňuje vytvoření nového souboru projektu pomocí sady Visual Studio. V této části vytvoříte soubor projektu Visual C#. Můžete místo toho vytvořte soubor projektu jazyka Visual Basic. V kontextu tohoto průvodce je rozdílem mezi těmito dvěma projektu soubory menší.

#### <a name="to-create-a-project-file"></a>Vytvoření souboru projektu

1.  Otevřete Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.

3.  V **nový projekt** dialogové okno, vyberte Visual C# typ projektu a pak vyberte **formulářové aplikace Windows** šablony. V **název** zadejte `BuildApp`. Zadejte **umístění** pro řešení, například `D:\`. Přijměte výchozí hodnoty pro **vytvořit adresář pro řešení** (zaškrtnuto), **přidat do správy zdrojového kódu** (není vybrána), a **název řešení** (`BuildApp`).

     Klikněte na tlačítko **OK** k vytvoření souboru projektu.

## <a name="examining-the-project-file"></a>V souboru projektu
 V předchozí části, Visual Studio jste použili k vytvoření souboru projektu Visual C#. Soubor projektu je reprezentována v **Průzkumníku řešení** uzel projektu s názvem BuildApp. Editor kódu aplikace Visual Studio můžete zkontrolovat soubor projektu.

#### <a name="to-examine-the-project-file"></a>Chcete-li zkontrolujte v souboru projektu

1.  V **Průzkumníku**, klikněte na uzel projektu BuildApp.

2.  V **vlastnosti** prohlížeče, Všimněte si, že **soubor projektu** vlastnost je BuildApp.csproj. Všechny soubory projektu jsou pojmenované s příponou "proj". Pokud jste vytvořili projektu jazyka Visual Basic, název souboru projektu by BuildApp.vbproj.

3.  Klikněte pravým tlačítkem na uzel projektu a pak klikněte na **uvolnit projekt**.

4.  Znovu klikněte pravým tlačítkem na uzel projektu a pak klikněte na **upravit BuildApp.csproj**.

     Soubor projektu se zobrazí v editoru kódu.

## <a name="targets-and-tasks"></a>Cílů a úloh
Soubory projektu jsou soubory formátu XML s kořenového uzlu [projektu](../msbuild/project-element-msbuild.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0"  xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
```

V elementu projektu musíte zadat obor názvů xmlns. Pokud `ToolsVersion` je k dispozici v nový projekt, musí být "15.0".

Vytváření aplikace práci s [cíl](../msbuild/target-element-msbuild.md) a [úloh](../msbuild/task-element-msbuild.md) elementy.

-   Úloha je nejmenší jednotku práce, jinými slovy, "atom" sestavení. Úlohy jsou nezávislé spustitelné součásti, které mohou mít vstupy a výstupy. Neexistují žádné úlohy aktuálně odkazuje nebo definované v souboru projektu. Přidání úkolů do souboru projektu v následujících částech. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md) tématu.

-   Cíl je pojmenované pořadí úloh. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md) tématu.

Výchozí cíl není definován v souboru projektu. Místo toho se vyskytuje v importovaných projekty. [Import](../msbuild/import-element-msbuild.md) element určuje importované projekty. Například v projektu jazyka C#, je výchozí cíl importovány ze souboru Microsoft.CSharp.targets.

```xml
<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
```

Importované soubory jsou efektivně vložena do souboru projektu, bez ohledu na jejich odkazují.

> [!NOTE]
> Některé typy projektů, jako je například .NET Core pomocí zjednodušené schéma s `Sdk` atribut místo `ToolsVersion`. Tyto projekty mají implicitní importy a různé výchozí hodnoty atributu.

MSBuild sleduje cíle sestavení a zaručuje, že každém cíli vychází více než jednou.

## <a name="adding-a-target-and-a-task"></a>Přidání cíle a úlohy
 Přidání cíle do souboru projektu. Přidáte úloha cíl, který vytiskne zprávu.

#### <a name="to-add-a-target-and-a-task"></a>Chcete-li přidat cíl a úlohy

1.  Přidejte tyto řádky k souboru projektu bezprostředně za příkaz importu:

    ```xml
    <Target Name="HelloWorld">
    </Target>
    ```

     Tím se vytvoří cíl s názvem Hello World. Všimněte si, že máte podporu technologie IntelliSense při úpravách souboru projektu.

2.  Přidejte řádky HelloWorld cíl, aby výsledná část vypadá takto:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Hello"></Message>  <Message Text="World"></Message>
    </Target>
    ```

3.  Uložte soubor projektu.

 Úloha zprávy je jedním z mnoha úloh, které se dodává s verzí nástroje MSBuild. Úplný seznam dostupných úloh a informace o použití najdete v části [– Reference úlohy](../msbuild/msbuild-task-reference.md).

 Úloha zprávy trvá řetězcovou hodnotu atributu Text jako vstup a zobrazí v zařízení výstup. Cíl HelloWorld provede úlohu zpráva dvakrát: nejdříve zobrazíte text "Hello" a potom zobrazíte "World".

## <a name="building-the-target"></a>Vytváření cíl
 Spuštění nástroje MSBuild z **Visual Studio – příkazový řádek** vytvořit cíl HelloWorld definované výše. Použijte přepínač příkazového řádku/Target nebo /t a vyberte cíl.

> [!NOTE]
>  Nemůžeme se budou vztahovat **Visual Studio – příkazový řádek** jako **příkazové okno** v následujících částech.

#### <a name="to-build-the-target"></a>K vytvoření cíle

1.  Klikněte na tlačítko **spustit**, pak klikněte na tlačítko **všechny programy**. Vyhledejte a vyberte možnost **Visual Studio – příkazový řádek** v **nástroje sady Visual Studio** složky.

2.  Z příkazového řádku přejděte do složky obsahující soubor projektu v takovém případě D:\BuildApp\BuildApp.

3.  Spusťte nástroje msbuild s /t:HelloWorld přepínač příkazu. To vybere a vytvoří HelloWorld cíle:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup v **příkazové okno**. Měli byste vidět dva řádky "Hello" a "World":

    ```
    Hello
    World
    ```

> [!NOTE]
>  Pokud místo toho uvidíte `The target "HelloWorld" does not exist in the project` pak jste zapomněli pravděpodobně k uložení souboru projektu v editoru kódu. Uložte soubor a zkuste to znovu.

 Podle střídavě editoru kódu a příkazové okno, můžete změnit soubor projektu a rychle zobrazit výsledky.

## <a name="build-properties"></a>Vlastnosti sestavení
 Vlastnosti sestavení jsou páry název hodnota, které průvodce sestavení. Několik vlastností sestavení, které jsou již definováni v horní části souboru projektu:

```xml
<PropertyGroup>
...
  <ProductVersion>10.0.11107</ProductVersion>
  <SchemaVersion>2.0</SchemaVersion>
  <ProjectGuid>{30E3C9D5-FD86-4691-A331-80EA5BA7E571}</ProjectGuid>
  <OutputType>WinExe</OutputType>
...
</PropertyGroup>
```

 Všechny vlastnosti jsou podřízené elementy PropertyGroup elementů. Název vlastnosti je název podřízený element a hodnota vlastnosti je text elementu podřízený element. Například

```xml
<TargetFrameworkVersion>v15.0</TargetFrameworkVersion>
```

 definuje vlastnost s názvem TargetFrameworkVersion, předá hodnotu řetězce "v15.0".

 Vytvoření vlastnosti může jej předefinovat kdykoli. If

```xml
<TargetFrameworkVersion>v3.5</TargetFrameworkVersion>
```

 Zobrazí se později v souboru projektu, nebo v souboru importu později v souboru projektu, pak TargetFrameworkVersion trvá nová hodnota "v3.5".

## <a name="examining-a-property-value"></a>Zkoumání hodnotu vlastnosti
 K získání hodnoty vlastnosti, použijte následující syntaxi, kde PropertyName je název vlastnosti:

```
$(PropertyName)
```

 Tuto syntaxi používají k prozkoumání některých vlastností v souboru projektu.

#### <a name="to-examine-a-property-value"></a>Chcete-li zkontrolovat hodnotu vlastnosti

1.  Z editoru kódu nahraďte cíl HelloWorld s tímto kódem:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Configuration is $(Configuration)" />
      <Message Text="MSBuildToolsPath is $(MSBuildToolsPath)" />
    </Target>
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tyto dva řádky (rozhraní .NET Framework verze se můžou lišit):

    ```
    Configuration is Debug
    MSBuildToolsPath is C:\Program Files (x86)\Microsoft Visual Studio\2017\<Visual Studio SKU>\MSBuild\15.0\Bin
    ```

> [!NOTE]
>  Pokud nevidíte tyto řádky pak jste pravděpodobně zapomněli k uložení souboru projektu v editoru kódu. Uložte soubor a zkuste to znovu.

### <a name="conditional-properties"></a>Podmíněné vlastnosti
 Mnoho vlastností, jako je konfigurace jsou definovány podmíněně, tedy atribut stav se zobrazí v prvku vlastnost. Podmíněné vlastnosti jsou definované nebo předefinovat pouze v případě, že je podmínka vyhodnocena jako "true". Všimněte si, že nedefinované vlastnosti mají výchozí hodnotu prázdný řetězec. Například

```xml
<Configuration   Condition=" '$(Configuration)' == '' ">Debug</Configuration>
```

 znamená "Pokud je vlastnost konfigurace ještě nebyl definován, je definovat a jako hodnotu"Ladění"".

 Téměř všechny elementy MSBuild může mít atribut podmínku. Další informace o používání atribut podmínku, najdete v článku [podmínky](../msbuild/msbuild-conditions.md).

### <a name="reserved-properties"></a>Rezervované vlastnosti
 MSBuild si vyhrazuje některé názvy vlastností k uložení informací o souboru projektu a binární soubory nástroje MSBuild. MSBuildToolsPath je příklad rezervované vlastnosti. Rezervované vlastnosti jsou odkazovány pomocí notace $ jako libovolné jiné vlastnosti. Další informace najdete v tématu [postupy: odkazování na název nebo umístění souboru projektu](../msbuild/how-to-reference-the-name-or-location-of-the-project-file.md) a [MSBuild vyhrazené a známé vlastnosti](../msbuild/msbuild-reserved-and-well-known-properties.md).

### <a name="environment-variables"></a>Proměnné prostředí
 Proměnné prostředí v souborech projektu můžete odkazovat stejným způsobem, jak vytvořit vlastnosti. Například pokud chcete použít proměnné prostředí PATH v souboru projektu, použijte $(cesta). Pokud projekt obsahuje definici vlastnosti, který má stejný název jako proměnné prostředí, vlastnost v projektu přepíše hodnotu proměnné prostředí. Další informace najdete v tématu [postupy: použití proměnných prostředí v sestavení](../msbuild/how-to-use-environment-variables-in-a-build.md).

## <a name="setting-properties-from-the-command-line"></a>Nastavení vlastností z příkazového řádku
 Vlastnosti mohou být definovány na příkazovém řádku pomocí /property nebo /p přepínač příkazového řádku. Hodnoty vlastností přijaté z příkazového řádku přepsat vlastnost hodnotami nastavenými v proměnné prostředí a soubor projektu.

#### <a name="to-set-a-property-value-from-the-command-line"></a>Chcete-li nastavit hodnotu vlastnosti z příkazového řádku

1.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld /p:Configuration=Release
    ```

2.  Zkontrolujte výstup příkazu. Měli byste vidět tento řádek:

    ```
    Configuration is Release.
    ```

 MSBuild vytvoří je vlastnost konfigurace a nastaví hodnotu "Verze".

## <a name="special-characters"></a>Speciální znaky
 Některé znaky mají zvláštní význam v souborech projektu nástroje MSBuild. Příklady tyto znaky: středníkem (;) a hvězdičky (*). Chcete-li použít tyto speciální znaky jako literály v souboru projektu, musí být zadán pomocí xx % syntaxe, kde xx představují šestnáctkové hodnoty ASCII znaku.

 Změňte úlohu zprávu zobrazíte hodnota vlastnosti konfigurace s speciální znaky, aby byl čitelnější.

#### <a name="to-use-special-characters-in-the-message-task"></a>Použít speciální znaky v úloha zprávy

1.  Z editoru kódu nahraďte obě úlohy zpráva tento řádek:

    ```xml
    <Message Text="%24(Configuration) is %22$(Configuration)%22" />
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tento řádek:

    ```
    $(Configuration) is "Debug"
    ```

 Další informace najdete v tématu [speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md).

## <a name="build-items"></a>Vytvoření položky
 Položka je část informace, obvykle název souboru, který se používá jako vstup systému sestavení. Kolekce položek představující zdrojové soubory například mohla být předána úkolů s názvem kompilace jejich kompilace do sestavení.

 Všechny položky jsou podřízené elementy ItemGroup elementů. Název položky je název podřízený element a hodnota položky je hodnota atributu zahrnout podřízeného elementu. Hodnoty položek se stejným názvem se shromažďují do typů položek s tímto názvem.  Například

```xml
<ItemGroup>
    <Compile Include="Program.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
</ItemGroup>
```

 Definuje skupinu položek obsahující dvě položky. Typ položky kompilace má dvě hodnoty: "Program.cs" a "Properties\AssemblyInfo.cs".

 Následující kód vytvoří stejný typ položky deklarace oba soubory v jeden atribut zahrnutí oddělené středníkem.

```xml
<ItemGroup>
    <Compile Include="Program.cs;Properties\AssemblyInfo.cs" />
</ItemGroup>
```

 Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).

> [!NOTE]
>  Cesty k souborům jsou relativní vzhledem ke složce obsahující soubor projektu nástroje MSBuild.

## <a name="examining-item-type-values"></a>Zkoumání hodnoty typu položky
 Chcete-li získat hodnoty typ položky, použijte následující syntaxi, kde typ položky je název typu položky:

```
@(ItemType)
```

 Pomocí této syntaxe zkontrolujte typ položky kompilace v souboru projektu.

#### <a name="to-examine-item-type-values"></a>K prozkoumání položka – Typ hodnoty

1.  Z editoru kódu nahraďte úlohu cíl HelloWorld s tímto kódem:

    ```xml
    <Target Name="HelloWorld">
      <Message Text="Compile item type contains @(Compile)" />
    </Target>
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tento dlouhý řádek:

    ```
    Compile item type contains Form1.cs;Form1.Designer.cs;Program.cs;Properties\AssemblyInfo.cs;Properties\Resources.Designer.cs;Properties\Settings.Designer.cs
    ```

 Hodnoty typu položky jsou odděleny středníky ve výchozím nastavení.

 Chcete-li změnit oddělovač typ položky, použijte následující syntaxi, kde typ položky je typ položky a oddělovače je řetězec znaků dělicí jeden nebo více:

```
@(ItemType, Separator)
```

 Změnit úloha zprávy a použít znak návratu na řádek informační kanály (% 0A %0 D) zobrazíte kompilace položky jeden na každý řádek.

#### <a name="to-display-item-type-values-one-per-line"></a>Chcete-li zobrazit typ položky hodnoty jeden na každý řádek

1.  Z editoru kódu nahraďte úloha zprávy tento řádek:

    ```xml
    <Message Text="Compile item type contains @(Compile, '%0A%0D')" />
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

     `msbuild buildapp.csproj /t:HelloWorld`

4.  Zkontrolujte výstup příkazu. Měli byste vidět tyto řádky:

    ```
    Compile item type contains Form1.cs
    Form1.Designer.cs
    Program.cs
    Properties\AssemblyInfo.cs
    Properties\Resources.Designer.cs
    Properties\Settings.Designer.cs
    ```

### <a name="include-exclude-and-wildcards"></a>Zahrnout, vyloučit a zástupné znaky
 Můžete použít zástupné znaky "*","\*\*", a "?" s atributem zahrnout k přidávání položek do typ položky. Například

```xml
<Photos Include="images\*.jpeg" />
```

 Přidá všechny soubory s příponou "JPEG" do složky bitových kopií typu položky fotografie, zatímco

```xml
<Photos Include="images\**.jpeg" />
```

 Typ položky fotografie přidá všechny soubory s příponou "JPEG" ve složce bitové kopie a všechny její podsložky. Další příklady najdete v tématu [postup: Vyberte soubory k sestavení](../msbuild/how-to-select-the-files-to-build.md).

 Všimněte si, že jsou deklarovaných položky budou přidány do typu položky. Například

```xml
<Photos Include="images\*.jpeg" />
<Photos Include="images\*.gif" />
```

 Vytvoří typ položky s názvem fotografií obsahující všechny soubory ve složce bitové kopie s příponou souboru "JPEG" nebo ".gif". Jde o ekvivalent následující řádek:

```xml
<Photos Include="images\*.jpeg;images\*.gif" />
```

 Můžete vyloučit položku z typ položky s atributem vyloučit. Například

```xml
<Compile Include="*.cs" Exclude="*Designer*">
```

 Přidá všechny soubory s příponou".cs" k položce kompilace typ, s výjimkou souborů, jejichž názvy obsahují řetězec "Designer". Další příklady najdete v tématu [postupy: vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md).

 Atribut vyloučení ovlivňuje pouze položky přidal atribut zahrnutí v elementu položku, která obsahuje oba. Například

```xml
<Compile Include="*.cs" />
<Compile Include="*.res" Exclude="Form1.cs">
```

 nebude vyloučení souboru Form1.cs, která byla přidána v předchozí položce elementu.

##### <a name="to-include-and-exclude-items"></a>Pro zahrnutí nebo vyloučení položek

1.  Z editoru kódu nahraďte úloha zprávy tento řádek:

    ```xml
    <Message Text="XFiles item type contains @(XFiles)" />
    ```

2.  Přidejte tuto skupinu položek jenom za elementem importu:

    ```xml
    <ItemGroup>
       <XFiles Include="*.cs;properties/*.resx" Exclude="*Designer*" />
    </ItemGroup>
    ```

3.  Uložte soubor projektu.

4.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

5.  Zkontrolujte výstup příkazu. Měli byste vidět tento řádek:

    ```
    XFiles item type contains Form1.cs;Program.cs;Properties/Resources.resx
    ```

## <a name="item-metadata"></a>Metadata položky
 Položky mohou obsahovat metadata kromě informace získané z atributy zahrnutí a vyloučení. Tato metadata lze úlohy, které vyžadují další informace o položkách než jenom hodnotu položky.

 Metadata položek je deklarován v souboru projektu vytvořením element s názvem metadat jako podřízený element položky. Položka může mít nula nebo více hodnot metadat. Například následující položku CSFile má metadata jazykové verze s hodnotou "Fr":

```xml
<ItemGroup>
    <CSFile Include="main.cs">
        <Culture>Fr</Culture>
    </CSFile>
</ItemGroup>
```

 Získat metadata hodnotu typ položky, použijte následující syntaxi, kde typ položky je název typu položky a MetaDataName je název metadat:

```
%(ItemType.MetaDataName)
```

#### <a name="to-examine-item-metadata"></a>Prozkoumat metadata položky

1.  Z editoru kódu nahraďte úloha zprávy tento řádek:

    ```xml
    <Message Text="Compile.DependentUpon: %(Compile.DependentUpon)" />
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tyto řádky:

    ```
    Compile.DependentUpon:
    Compile.DependentUpon: Form1.cs
    Compile.DependentUpon: Resources.resx
    Compile.DependentUpon: Settings.settings
    ```

 Všimněte si, jak frázi "Compile.DependentUpon" zobrazuje několikrát. Používání metadat pomocí této syntaxe v rámci cíl způsobí, že "dávkování". Dávkování znamená po provedení úlohy v rámci cíle pro každou hodnotu jedinečný metadat. To je ekvivalentní skriptu MSBuild nejběžnější "smyčka" for programovací konstrukce. Další informace najdete v tématu [Batching](../msbuild/msbuild-batching.md).

### <a name="well-known-metadata"></a>Well-Known Metadata
 Vždy, když je přidat položku do seznamu položek, že položka není přiřazen některé známé metadat. Například %(Filename) vrátí název souboru žádné položky. Úplný seznam známých metadata, najdete v části [Metadata známé položky](../msbuild/msbuild-well-known-item-metadata.md).

##### <a name="to-examine-well-known-metadata"></a>K prozkoumání dobře známé metadat

1.  Z editoru kódu nahraďte úloha zprávy tento řádek:

    ```xml
    <Message Text="Compile Filename: %(Compile.Filename)" />
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tyto řádky:

    ```
    Compile Filename: Form1
    Compile Filename: Form1.Designer
    Compile Filename: Program
    Compile Filename: AssemblyInfo
    Compile Filename: Resources.Designer
    Compile Filename: Settings.Designer
    ```

 Srovnáním výše uvedených dvou příkladech se zobrazí, ne každá položka v typ položky kompilace se DependentUpon metadata, všechny položky mít dobře známé Filename metadata.

### <a name="metadata-transformations"></a>Metadata transformace
 Položky seznamů lze je transformovat do nové položky seznamů. K transformaci seznam položek, použijte následující syntaxi, kde typ položky je název typu položky a MetadataName je název metadat:

```
@(ItemType -> '%(MetadataName)')
```

 Například seznam položek zdrojových souborů je možné převést na kolekci objektů souborů pomocí výrazu jako `@(SourceFiles -> '%(Filename).obj')`. Další informace najdete v tématu [transformuje](../msbuild/msbuild-transforms.md).

##### <a name="to-transform-items-using-metadata"></a>K transformaci položek pomocí metadat

1.  Z editoru kódu nahraďte úloha zprávy tento řádek:

    ```xml
    <Message Text="Backup files: @(Compile->'%(filename).bak')" />
    ```

2.  Uložte soubor projektu.

3.  Z **příkazové okno**, zadejte a spouštět tento řádek:

    ```
    msbuild buildapp.csproj /t:HelloWorld
    ```

4.  Zkontrolujte výstup příkazu. Měli byste vidět tento řádek:

    ```
    Backup files: Form1.bak;Form1.Designer.bak;Program.bak;AssemblyInfo.bak;Resources.Designer.bak;Settings.Designer.bak
    ```

 Všimněte si, že metadata vyjádřené v této syntaxe nezpůsobí dávkování.

## <a name="whats-next"></a>Co je další?
 Zjistěte, jak vytvořit jednoduché projektu krok jeden soubor současně, vyzkoušejte [návod: vytvoření souboru projektu MSBuild od začátku](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md).

## <a name="see-also"></a>Viz také

- [Přehled nástroje MSBuild](../msbuild/msbuild.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
