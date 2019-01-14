---
title: -Project (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /Project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- Project Devenv switch (/Project)
- Devenv, /Project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1706d8dade02bd7f247d7f2ce163955615a3b0f3
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269183"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)

Identifikuje jediného projektu v rámci konfigurace zadané řešení sestavení, vyčištění, znovu sestavit nebo nasadit.

## <a name="syntax"></a>Syntaxe

```shell
devenv SolutionName {/Build|/Clean|/Deploy|/Rebuild} [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Povinný parametr. Úplná cesta a název souboru řešení.

- {`/Build`|`/Clean`|`/Deploy`|`/Rebuild`}

  Povinný parametr. [Sestaví](build-devenv-exe.md), [vyčistí](clean-devenv-exe.md), [nasadí](deploy-devenv-exe.md), nebo [znovu sestaví](rebuild-devenv-exe.md) projektu.

- *SolnConfigName*

  Volitelné. Název konfigurace řešení (například `Debug` nebo `Release`) použít pro řešení s názvem v *SolutionName*. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud tento argument není zadána nebo prázdný řetězec (`""`), nástroj použije aktivní konfigurace řešení.

- `/Project` *ProjName*

  Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat zobrazovaný název projektu nebo relativní cesta z *SolutionName* složku do souboru projektu. Můžete také zadat úplnou cestu a název souboru projektu.

- `/ProjectConfig` *ProjConfigName*

  Volitelné. Název konfigurace sestavení projektu (například `Debug` nebo `Release`) použít `/Project` s názvem. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`).

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

- Musí být použita součástí `devenv` `/Build`, `/Clean`, `/Rebuild`, nebo `/Deploy` příkazu.

- Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

- Souhrnné informace o sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/Out` přepnout.

## <a name="example"></a>Příklad

Tento příklad vytvoří projekt `CSharpWinApp`, použije `Debug` konfigurace sestavení projektu v rámci `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)