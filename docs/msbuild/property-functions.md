---
title: Funkce vlastností | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, property functions
ms.assetid: 2253956e-3ae0-4bdc-9d3a-4881dfae4ddb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc1665b0b5a12f8e1719116e61f13ac915083c0d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31978216"
---
# <a name="property-functions"></a>Funkce vlastností

V rozhraní .NET Framework verze 4 a 4.5 funkce vlastností slouží k vyhodnocení nástroje MSBuild skripty. Funkce vlastností lze použít bez ohledu na vlastnosti se zobrazí. Na rozdíl od úloh funkce vlastností bylo možné použít mimo cíle a vyhodnocují před spuštěním jakékoli cíl.

 Bez použití úlohy nástroje MSBuild, můžete číst systémového času, porovnání řetězců, regulární výrazy shody a provádět další akce ve vašem skriptu sestavení. MSBuild se pokusí převést řetězec na číslo a číslo na řetězec a ujistěte se, jiné převody podle potřeby.

## <a name="property-function-syntax"></a>Syntaxe funkce vlastností

Toto jsou tři druhy funkce vlastností; jednotlivé funkce má jinou syntaxi:

- Funkce vlastností řetězce (instance)
- Funkce statických vlastností
- Funkce vlastností nástroje MSBuild

### <a name="string-property-functions"></a>Funkce vlastností řetězce

Všechny hodnoty vlastností sestavení jsou pouze hodnoty řetězců. Metody řetězců (instance) můžete použít k provozu na žádnou hodnotu vlastnosti. Název jednotky (prvních tří znaků) může například extrahovat z vlastnosti sestavení, která představuje úplnou cestu s využitím tento kód:

```fundamental
$(ProjectOutputFolder.Substring(0,3))
```

### <a name="static-property-functions"></a>Funkce statických vlastností

Ve vašem skriptu sestavení získat přístup k statické vlastnosti a metody třídy mnoho systému. Chcete-li získat hodnotu pomocí statické vlastnosti, použijte následující syntaxi, kde *třída* je název třídy systému a *vlastnost* je název vlastnosti.

```fundamental
$([Class]::Property)
```

Například můžete použít následující kód k nastavení vlastnosti sestavení na aktuální datum a čas.

```xml
<Today>$([System.DateTime]::Now)</Today>
```

Zavolejte statickou metodu, použijte následující syntaxi, kde *třída* je název systémové třídy *metoda* je název metody, a *(parametry)* je seznam parametrů pro metodu:

```fundamental
$([Class]::Method(Parameters))
```

Nastavit vlastnost sestavení na nový identifikátor GUID, například můžete použít tento skript:

```xml
<NewGuid>$([System.Guid]::NewGuid())</NewGuid>
```

Statické vlastnosti funkcí můžete použít všechny statické metody nebo vlastnosti těchto tříd systému:

- System.Byte
- System.Char
- System.Convert
- System.DateTime
- System.Decimal
- System.Double
- System.Enum
- System.Guid
- System.Int16
- System.Int32
- System.Int64
- System.IO.Path
- System.Math
- System.Runtime.InteropServices.OSPlatform
- System.Runtime.InteropServices.RuntimeInformation
- System.UInt16
- System.UInt32
- System.UInt64
- System.SByte
- System.Single
- System.String
- System.StringComparer
- System.TimeSpan
- System.Text.RegularExpressions.Regex
- System.UriBuilder
- System.Version
- Microsoft.Build.Utilities.ToolLocationHelper

Kromě toho můžete použít následující statické metody a vlastnosti:

- System.Environment::CommandLine
- System.Environment::ExpandEnvironmentVariables
- System.Environment::GetEnvironmentVariable
- System.Environment::GetEnvironmentVariables
- System.Environment::GetFolderPath
- System.Environment::GetLogicalDrives
- System.IO.Directory::GetDirectories
- System.IO.Directory::GetFiles
- System.IO.Directory::GetLastAccessTime
- System.IO.Directory::GetLastWriteTime
- System.IO.Directory::GetParent
- System.IO.File::Exists
- System.IO.File::GetCreationTime
- System.IO.File::GetAttributes
- System.IO.File::GetLastAccessTime
- System.IO.File::GetLastWriteTime
- System.IO.File::ReadAllText

### <a name="calling-instance-methods-on-static-properties"></a>Volání metody Instance na statické vlastnosti

Pokud máte přístup k statické vlastnosti, která vrátí instanci objektu, můžete vyvolat metodu instance tohoto objektu. K vyvolání metody instance, použijte následující syntaxi, kde *třída* je název systémové třídy *vlastnost* je název vlastnosti, *metoda* je název Metoda, a *(parametry)* je seznam parametrů pro metodu:

```fundamental
$([Class]::Property.Method(Parameters))
```

Název třídy musí být plně kvalifikovaný s oborem názvů.

Například můžete použít následující kód k nastavení vlastnosti sestavení dnes na aktuální datum.

```xml
<Today>$([System.DateTime]::Now.ToString("yyyy.MM.dd"))</Today>
```

### <a name="msbuild-property-functions"></a>Funkce vlastností nástroje MSBuild

Několik statických metod v buildu je přístupná zajistit aritmetický bitový logické a podpora řídicí znak. Tyto metody přistupujete pomocí následující syntaxe, kde *metoda* je název metody a *parametry* je seznam parametrů pro metodu.

```fundamental
$([MSBuild]::Method(Parameters))
```

Například pokud chcete přidat společně dvě vlastnosti, které mají číselné hodnoty, použijte následující kód.

```fundamental
$([MSBuild]::Add($(NumberOne), $(NumberTwo))
```

Tady je seznam funkcí nástroje MSBuild vlastnost:

|Podpis funkce|Popis|
|------------------------|-----------------|
|Double přidat (double, dvojitou b)|Přidáte dvě hodnoty Double.|
|dlouho přidáte (dlouho a, b dlouho)|Přidejte dva dlouhé.|
|Double odečtena (double, dvojitou b)|Odečtena dvě hodnoty Double.|
|dlouho odečtena (dlouho a, b dlouho)|Odečtena dva dlouhé.|
|Double násobení (double, dvojitou b)|Vynásobte hodnoty dvou Double.|
|dlouho násobení (dlouho, long b)|Vynásobte dva dlouhé.|
|Double rozdělení (double, dvojitou b)|Dělení dvou hodnoty Double.|
|Dlouhé dělení (dlouho, long b)|Dělení dvou dlouhé.|
|dvojité Modulo (double, dvojitou b)|Modulo dvě hodnoty Double.|
|dlouho Modulo (dlouho, long b)|Modulo dva dlouhé.|
|řetězec Escape(string unescaped)|Ukončení řetězce podle MSBuild útěku pravidel.|
|řetězec Unescape (řetězec uvozený)|Unescape – řetězec podle MSBuild útěku pravidel.|
|int BitwiseOr (int první, int sekundu)|Provedení bitové operace `OR` v prvním a druhém (první &#124; druhý).|
|int BitwiseAnd (int první, int sekundu)|Provedení bitové operace `AND` na první a druhé (první a druhý).|
|int BitwiseXor (int první, int sekundu)|Provedení bitové operace `XOR` v prvním a druhém (první ^ druhý).|
|int BitwiseNot(int first)|Provedení bitové operace `NOT` (~ první).|
|BOOL IsOsPlatform (platformString řetězec)|Určete, zda je aktuální platforma operačního systému `platformString`. `platformString` musí být členem skupiny <xref:System.Runtime.InteropServices.OSPlatform>.|
|bool IsOSUnixLike|Hodnota TRUE, pokud aktuální operační systém je v systému Unix.|
|řetězec NormalizePath (cesta parametry řetězec [])|Získá kanonizovaného úplnou cestu zadaná cesta a zajišťuje, že obsahuje znaků oddělujících správném adresáři pro aktuální operační systém.|
|řetězec NormalizeDirectory (cesta parametry řetězec [])|Získá kanonizovaného úplnou cestu k adresáři zadaná a zajišťuje obsahuje znaků oddělujících správném adresáři pro aktuální operační systém a zajistit jeho obsahuje koncové lomítko.|
|řetězec EnsureTrailingSlash(string path)|Pokud zadaná cesta k nemá ho přidat koncové lomítko. Pokud cesta je prázdný řetězec, nebude změněno.|
|řetězec GetPathOfFileAbove (soubor řetězec, řetězec startingDirectory)|Vyhledá soubor na základě umístění aktuální soubor sestavení nebo na základě `startingDirectory`, je-li zadána.|
|GetDirectoryNameOfFileAbove (startingDirectory řetězec, řetězec fileName)|Vyhledejte soubor v zadaný adresář nebo umístění struktury adresářů výše tohoto adresáře.|
|řetězec MakeRelative (basePath řetězec, řetězec cesty)|Díky `path` vzhledem k `basePath`. `basePath` musí být absolutní adresáře. Pokud `path` nesmí být vytvářeny relativní, je vrácen typu verbatim. Podobně jako `Uri.MakeRelativeUri`.|
|řetězec ValueOrDefault (conditionValue řetězec, řetězec defaultValue)|Vrátí řetězec v parametru 'defaultValue' pouze v případě, že parametr 'conditionValue' je prázdný, jinak, vrátí hodnotu conditionValue.|

##  <a name="nested-property-functions"></a>Vnořené vlastnosti funkce

Funkce vlastností formuláře složitější funguje, jak ukazuje následující příklad můžete kombinovat.

```fundamental
$([MSBuild]::BitwiseAnd(32, $([System.IO.File]::GetAttributes(tempFile))))
```

Vrátí hodnotu v tomto příkladu <xref:System.IO.FileAttributes> `Archive` bit (32 nebo 0) v zadané cestě soubor `tempFile`. Všimněte si, že data výčtové hodnoty nemůže být použit podle názvu v rámci funkce vlastností. Místo toho musíte použít číselnou hodnotu (32).

Metadata může také zobrazit funkce vnořené vlastnosti. Další informace najdete v tématu [Batching](../msbuild/msbuild-batching.md).

## <a name="msbuild-doestaskhostexist"></a>MSBuild DoesTaskHostExist

`DoesTaskHostExist` Vlastnost funkce v nástroji MSBuild vrátí, zda hostitel úloh je aktuálně nainstalována zadaných hodnot runtime a architektura.

Tato vlastnost funkce má následující syntaxi:

```fundamental
$([MSBuild]::DoesTaskHostExist(string theRuntime, string theArchitecture))
```

## <a name="msbuild-ensuretrailingslash"></a>EnsureTrailingSlash nástroje MSBuild

`EnsureTrailingSlash` Vlastnost funkce v nástroji MSBuild přidá koncové lomítko, pokud dosud neexistuje.

Tato vlastnost funkce má následující syntaxi:

```fundamental
$([MSBuild]::EnsureTrailingSlash('$(PathProperty)'))
```

## <a name="msbuild-getdirectorynameoffileabove"></a>MSBuild GetDirectoryNameOfFileAbove

MSBuild `GetDirectoryNameOfFileAbove` vlastnost funkce hledá soubor v adresáři vyšší než aktuální adresář v cestě.

 Tato vlastnost funkce má následující syntaxi:

```fundamental
$([MSBuild]::GetDirectoryNameOfFileAbove(string ThePath, string TheFile))
```

 Následující kód je příkladem této syntaxe.

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))\EnlistmentInfo.props" Condition=" '$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))' != '' " />
```

## <a name="msbuild-getpathoffileabove"></a>GetPathOfFileAbove nástroje MSBuild

`GetPathOfFileAbove` Vlastnost funkce v nástroji MSBuild vrací cestu k souboru, všechny předcházející. Je funkčně odpovídá volání

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />
```

Tato vlastnost funkce má následující syntaxi:

```fundamental
$([MSBuild]::GetPathOfFileAbove(dir.props))
```

## <a name="msbuild-getregistryvalue"></a>GetRegistryValue nástroje MSBuild

MSBuild `GetRegistryValue` vlastnost funkce vrátí hodnotu klíče registru. Tato funkce přebírá dva argumenty, název klíče a hodnoty název a vrací hodnotu z registru. Pokud nezadáte název hodnoty, je vrácen výchozí hodnota.

Následující příklady ukazují, jak tato funkce slouží:

```fundamental
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, ``))                                  // default value
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, `SymbolCacheDir`))
$([MSBuild]::GetRegistryValue(`HKEY_LOCAL_MACHINE\SOFTWARE\(SampleName)`, `(SampleValue)`))             // parens in name and value
```

## <a name="msbuild-getregistryvaluefromview"></a>GetRegistryValueFromView nástroje MSBuild

MSBuild `GetRegistryValueFromView` funkce vlastnost získá data registru systému zadána klíč registru, hodnotu a jeden nebo více seřazených registru zobrazení. Klíč a hodnotu vyhledávají v každém zobrazení registru v pořadí, dokud se nacházejí.

Syntaxe pro tuto funkci vlastnost je:

```fundamental
[MSBuild]::GetRegistryValueFromView(string keyName, string valueName, object defaultValue, params object[] views)
```

Operační systém Windows 64-bit udržuje HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node klíč registru, který představuje zobrazení HKEY_LOCAL_MACHINE\SOFTWARE registru pro 32bitové aplikace.

Ve výchozím nastavení 32bitové aplikace běžící v WOW64 přistupuje k zobrazení 32bitového registru a 64-bit aplikace přistupuje k zobrazení 64-bit registru.

K dispozici jsou následující zobrazení registru:

|Zobrazení registru|Definice|
|-------------------|----------------|
|RegistryView.Registry32|Zobrazení registru 32bitovou aplikaci.|
|RegistryView.Registry64|Zobrazení registru 64bitových aplikací.|
|RegistryView.Default|Zobrazení registru, které odpovídá proces, který je aplikace spuštěna v.|

Následuje příklad.

 ```fundamental
$([MSBuild]::GetRegistryValueFromView('HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SDKs\Silverlight\v3.0\ReferenceAssemblies', 'SLRuntimeInstallPath', null, RegistryView.Registry64, RegistryView.Registry32))
```

získá data SLRuntimeInstallPath ReferenceAssemblies klíče, nejprve v zobrazení 64-bit registru a pak v zobrazení 32bitového registru.

## <a name="msbuild-makerelative"></a>MakeRelative nástroje MSBuild

MSBuild `MakeRelative` funkce vlastnost vrací relativní cesta relativní cesta k první druhý cestu. Každá cesta může být souboru nebo složce.

Tato vlastnost funkce má následující syntaxi:

```fundamental
$([MSBuild]::MakeRelative($(FileOrFolderPath1), $(FileOrFolderPath2)))
```

Následující kód je příkladem této syntaxe.

```xml
<PropertyGroup>
    <Path1>c:\users\</Path1>
    <Path2>c:\users\username\</Path2>
</PropertyGroup>

<Target Name = "Go">
    <Message Text ="$([MSBuild]::MakeRelative($(Path1), $(Path2)))" />
    <Message Text ="$([MSBuild]::MakeRelative($(Path2), $(Path1)))" />
</Target>

<!--
Output:
   username\
   ..\
-->
```

## <a name="msbuild-valueordefault"></a>ValueOrDefault nástroje MSBuild

MSBuild `ValueOrDefault` funkce vlastnost vrací první argument, pokud je null nebo prázdný. Pokud první argument je null nebo prázdná, vrátí funkce druhý argument.

Následující příklad ukazuje, jak tuto funkci používat.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <Value1>$([MSBuild]::ValueOrDefault(`$(UndefinedValue)`, `a`))</Value1>
        <Value2>$([MSBuild]::ValueOrDefault(`b`, `$(Value1)`))</Value2>
    </PropertyGroup>

    <Target Name="MyTarget">
        <Message Text="Value1 = $(Value1)" />
        <Message Text="Value2 = $(Value2)" />
    </Target>
</Project>

<!--
Output:
  Value1 = a
  Value2 = b
-->
```

## <a name="see-also"></a>Viz také

[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)
[přehled nástroje MSBuild](../msbuild/msbuild.md)
