---
title: Přizpůsobení systému sestavení
description: Tento článek je stručný úvod do MSBuild sestavení systém používaný v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 6958B102-8527-4B40-BC65-3505DB63F9D3
ms.openlocfilehash: e999c9c68a534611aa1db6e571594d11fc20201e
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="customizing-the-build-system"></a>Přizpůsobení systému sestavení

MSbuild je modul sestavení vyvinuté společností Microsoft, který umožňuje vytvářet především aplikací .NET. Rozhraní Mono má také vlastní implementaci společnosti Microsoft Build Engine, nazývá **xbuild**. Ale xbuild byla ukončena, považuje pomocí nástroje MSBuild ve všech operačních systémech.

**MSbuild** používá primárně u jako systém sestavení pro projekty v sadě Visual Studio for Mac. 

MSBuild funguje tak, že trvá sadu vstupy, jako je například zdrojové soubory a transformuje je výstupů, jako je například spustitelné soubory. Tento výstup dosahuje vyvolání nástroje, jako je kompilátoru. 


## <a name="msbuild-file"></a>Soubor nástroje MSBuild

MSBuild používá soubor XML, názvem souboru projektu, který definuje *položky* které jsou součástí projektu (například obrázek prostředky) a *vlastnosti* potřebné k sestavení projektu. Tento projektový soubor bude mít vždy příponu souboru končí na `proj`, jako například `.csproj` pro projekty C#. 

### <a name="viewing-the-msbuild-file"></a>Prohlížení souboru nástroje MSBuild

Vyhledejte soubor MSBuild kliknutím pravým tlačítkem myši na název projektu a výběrem **odhalit v hledání**. V okně funkce hledání se zobrazí všechny soubory a složky související s projektem, včetně `.csproj` souboru, jak je znázorněno na následujícím obrázku:

![](media/customizing-build-system-image1.png)

Chcete-li zobrazit `.csproj` na nové záložce v sadě Visual Studio pro Mac, klikněte pravým tlačítkem na název projektu a přejděte do **nástroje > Upravit soubor**:

![](media/customizing-build-system-image2.png)

### <a name="composition-of-the-msbuild-file"></a>Složení souboru nástroje MSBuild

Všechny soubory nástroje MSBuild obsahovat povinné kořenové `Project` elementu, například takto:

```
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="14.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
</Project>
```

Obvykle se také importovat projekt `.targets` souboru. Tento soubor obsahuje řadu pravidel, které popisují, jak zpracovat a vytvářet různé soubory. Import se obvykle zobrazují směrem k dolní části vaší `proj` souboru, a pro projekty C# vypadat přibližně takto:

```
<Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
```

Soubor cíle je jiného souboru MSBuild. Tento soubor obsahuje MSBuild kód, který je ve více projektech opakovaně použitelné. Například `Microsoft.CSharp.targets` soubor, který se nachází v adresáři reprezentována `MSBuildBinPath` vlastnost (nebo proměnná), obsahuje logiku pro vytváření sestavení C# ze zdrojových souborů C#.

### <a name="items-and-properties"></a>Položky a vlastnosti

Existují dva základní datové typy v nástroji MSBuild: *položky* a *vlastnosti*, které jsou vysvětlené podrobněji v následujících částech.

#### <a name="properties"></a>Vlastnosti

Vlastnosti jsou páry klíč/hodnota, které se používají k ukládání nastavení, které ovlivňují kompilace, jako je například – možnosti kompilátoru.

Jsou nastavené, použití PropertyGroup a může obsahovat libovolný počet PropertiesGroups, která může obsahovat libovolný počet vlastnosti. 

PropertyGroup – pro jednoduché konzolové aplikace může například vypadat jako následující kód XML:

```
<PropertyGroup>
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
        <Platform Condition=" '$(Platform)' == '' ">x86</Platform>
        <ProjectGuid>{E248730E-1393-43CC-9183-FFA42F63BE81}</ProjectGuid>
        <OutputType>Exe</OutputType>
        <RootNamespace>refactoring</RootNamespace>
        <AssemblyName>refactoring</AssemblyName>
        <TargetFrameworkVersion>v4.5</TargetFrameworkVersion>
    </PropertyGroup>
```

Vlastnosti lze odkazovat z výrazů pomocí `$()` syntaxe. Například `$(Foo)` se vyhodnotí jako hodnotu `Foo` vlastnost. Pokud nebyla nastavena vlastnost, bude vyhodnocena jako prázdný řetězec, bez jakékoli chyby.

#### <a name="items"></a>Položky

Položky představují způsob, jak se zabývá vstupy do sestavení systému, jako jsou uvedeny nebo nastaví a obvykle představují soubory. Každá položka má položku *typ*, položku *specifikace*a volitelné libovolný *metadata*. Všimněte si, že MSBuild nepracuje na jednotlivé položky trvá na všechny položky zadaný typ označuje položku *nastavit*

Položky jsou vytvořené pomocí deklarace `ItemGroup`. Může existovat libovolný počet ItemGroups, která může obsahovat libovolný počet položek. 

Například následující fragment kódu vytvoří iOS spusťte obrazovky. Spusťte obrazovky mít typ sestavení `BundleResource`, s specifikace jako cestu k bitové kopii:

```
 <ItemGroup>
    <BundleResource Include="Resources\Default-568h%402x.png" />
    <BundleResource Include="Resources\Default%402x.png" />
    <BundleResource Include="Resources\Default.png" />
    <BundleResource Include="Resources\Default-Portrait.png" />
    <BundleResource Include="Resources\Default-Portrait%402x.png" />
    <BundleResource Include="Resources\Default-Landscape%402x.png" />
  </ItemGroup>
 ```
 
 Položku sady lze odkazovat z výrazů pomocí `@()` syntaxe. Například `@(BundleResource)` se vyhodnotí jako sada položek BundleResource, což znamená, že všechna BundleResource položek. Pokud neexistují žádné položky tohoto typu, bude prázdný, bez jakékoli chyby.

## <a name="resources-for-learning-msbuild"></a>Zdroje informací nástroje MSBuild

Další informace o nástroji MSBuild podrobněji lze použít v následujících zdrojích informací:

* [MSDN – přehled](https://msdn.microsoft.com/library/dd393574.aspx)
* [MSDN – koncepty](https://msdn.microsoft.com/library/dd637714.aspx)


