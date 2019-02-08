---
title: -ProjectConfig (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /ProjectConfig Devenv switch
- configurations, rebuilding
- deployment projects, creating
- configurations, cleaning
- deployment projects, specifying
- deployment projects, adding
- build configurations, specifying
- Devenv, /ProjectConfig switch
- ProjectConfig Devenv switch (/ProjectConfig)
- projects [Visual Studio], build configuration
- projects [Visual Studio], cleaning
ms.assetid: 6b54ef59-ffed-4f62-a645-1279ede97ebf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6127be41e4b791fa03182b65ab78c9814e16d30
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55954215"
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)

Určuje konfiguraci sestavení projektu, kterou chcete použít při sestavení, vyčištění, znovu sestavit nebo nasadit projekt s názvem v `/Project` argument.

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

  Volitelné. Název konfigurace řešení (například `Debug` nebo `Release`) použít k řešení s názvem v *SolutionName*. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud tento argument není zadána nebo prázdný řetězec (`""`), nástroj použije aktivní konfigurace řešení.

- `/Project` *ProjName*

  Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat zobrazovaný název projektu nebo relativní cesta z *SolutionName* složku do souboru projektu. Můžete také zadat úplnou cestu a název souboru projektu.

- `/ProjectConfig` *ProjConfigName*

  Volitelné. Název konfigurace sestavení projektu (například `Debug` nebo `Release`) použít `/Project` s názvem. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`).

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

`/ProjectConfig` Přepínač musí použít společně s `/Project` přepnout jako součást `/Build`, /`Clean`, `/Deploy`, nebo `/Rebuild` příkazu.

Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

Souhrnné informace o sestavení, včetně chyb, lze zobrazit, v příkazovém okně nebo do jakéhokoli souboru protokolu zadaný `/Out` přepnout.

## <a name="example"></a>Příklad

Následující příkaz sestaví projekt `CSharpWinApp`, použije `Debug` konfigurace sestavení projektu v rámci `MySolution`:

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)