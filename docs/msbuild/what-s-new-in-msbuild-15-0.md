---
title: "Jaký & č. 39; s nového v nástroji MSBuild 15 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9976b6fd-d052-4017-b848-35b5bf4b2f66
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 19b7c821f708267d4827d06858b63128ce747ac3
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="whats-new-in-msbuild-15"></a>Co je nového v nástroji MSBuild 15
MSBuild je nyní k dispozici jako součást [.NET Core SDK](https://www.microsoft.com/net/download/core) a mohou vytvářet projekty .NET Core v systému Windows, systému macOS a Linux.  

## <a name="changed-path"></a>Změněné cesta
 MSBuild je nyní nainstalován do složky v rámci jednotlivých verzí sady Visual Studio. Například `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\MSBuild`. Můžete taky následující modul prostředí PowerShell najít MSBuild: [vssetup.powershell](https://github.com/Microsoft/vssetup.powershell).

 MSBuild je již nainstalována v globální mezipaměti sestavení. Chcete-li MSBuild prostřednictvím kódu programu, použijte balíčky NuGet.

## <a name="changed-properties"></a>Změněné vlastnosti  
 Následující vlastnosti nástroje MSBuild bylo aktualizováno z důvodu nové číslo verze.  

-   `MSBuildToolsVersion`pro tuto verzi nástroje je 15.0. Verze sestavení je 15.1.0.0.

-   `MSBuildToolsPath`již má pevnou umístění. Ve výchozím nastavení je umístěný ve složce MSBuild\15.0\Bin relativní k umístění instalace sady Visual Studio, ale čas instalace sady Visual Studio lze změnit umístění instalace.

-   `ToolsVersion`hodnoty jsou již nastaveny v registru.  

-   `SDK35ToolsPath` a `SDK40ToolsPath` vlastnosti bodu na rozhraní .NET Framework SDK, který je součástí balíčku tato verze sady Visual Studio (například 10.0A nástroje 4.X).  

## <a name="updates"></a>Aktualizace
- [Element projektu](../msbuild/project-element-msbuild.md) má nový `SDK` atribut. Také `Xmlns` atribut je volitelný.
- [Položka Element](../msbuild/item-element-msbuild.md) mimo cíle má nový `Update` atribut. Také omezení na `Remove` atribut se odstranilo.
- `Directory.Build.props`je soubor definovaný uživatelem, který poskytuje přizpůsobení projektů adresáře. Tento soubor je automaticky importovány ze Microsoft.Common.props, pokud vlastnost `ImportDirectoryBuildTargets` je nastaven na **false**. `Directory.Build.targets`importovaných pomocí Microsoft.Common.targets.
- Veškerá metadata, s názvem, který není v konfliktu s aktuální seznam atributů může být volitelně vyjádřený jako atribut. Další informace najdete v tématu [Item – prvek](../msbuild/item-element-msbuild.md).

## <a name="new-property-functions"></a>Nové funkce vlastností

- `EnsureTrailingSlash`Přidá koncové lomítko na cestu, pokud dosud neexistuje.
- `NormalizePath`kombinuje části cesty a zajistí, že má výstupní řetězec znaků oddělujících správném adresáři pro aktuální operační systém.
- `NormalizeDirectory`kombinuje části cesty, zajišťuje koncové lomítko a zajistí, že má výstupní řetězec znaků oddělujících správném adresáři pro aktuální operační systém.
- `GetPathOfFileAbove`vrátí cestu k souboru, všechny předcházející. Je funkčně odpovídá volání`<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />`

## <a name="see-also"></a>Viz také
[MSBuild](../msbuild/msbuild.md)
