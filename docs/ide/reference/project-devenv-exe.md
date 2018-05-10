---
title: -Projektu (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 588b56c03dbd14b1b7658b92a67b02a6dc3892eb
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
Určuje jeden projekt v rámci zadaného řešení konfigurace sestavení, vyčistit, znovu sestavit nebo nasadit.

## <a name="syntax"></a>Syntaxe

```cmd
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Arguments
 / Build

 Sestavení projektu určeného `/project` `ProjName`.

 / clean

 Odstraní všechny zprostředkující soubory a adresáře výstup vytvořené během sestavení.

 / rebuild

 Vyčistí pak sestavení projektu určeného `/project` `ProjName`.

 / nasazení

 Určuje, že projekt nasazen po sestavení nebo opětovném sestavení.

 `SolnConfigName`

 Požadováno. Název konfigurace řešení, které se použijí k řešení s názvem v `SolutionName`.

 `SolutionName`

 Požadováno. Úplná cesta a název souboru, řešení.

 / Project `ProjName`

 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.

 / projectconfig – `ProjConfigName`

 Volitelné. Konfigurace, které má být použita pro sestavení název projektu `/project` s názvem.

## <a name="remarks"></a>Poznámky

-   Musí použít součástí `devenv /build`, nebo`clean`, `/rebuild`, nebo `/deploy` příkaz.

-   Uzavřete řetězců, které obsahují mezery v uvozovkách.

-   Souhrnné informace o sestavení, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.

## <a name="example"></a>Příklad
 Tento příklad vytvoří projekt `CSharpConsoleApp`pomocí `Debug` konfigurace sestavení projektu v rámci `Debug` konfiguraci řešení `MySolution`.

```cmd
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Nasadit (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)