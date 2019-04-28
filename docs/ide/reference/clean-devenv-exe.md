---
title: -Clean (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- builds [Team System], cleaning files
- Clean Devenv switch
- /Clean Devenv switch
- Devenv, /Clean switch
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 810f05b0838f27004bee983dc0acf7a3009e22a0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62573089"
---
# <a name="clean-devenvexe"></a>/Clean (devenv.exe)

Vyčistí všechny zprostředkující soubory a výstupní adresáře.

## <a name="syntax"></a>Syntaxe

```shell
devenv SolutionName /Clean [Config [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Povinný parametr. Úplná cesta a název souboru řešení.

- *Konfigurace*

  Volitelné. Konfigurace (například `Debug` nebo `Release`) k vyčištění zprostředkující soubory pro řešení s názvem v *SolutionName*. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud tento argument není zadána nebo prázdný řetězec (`""`), nástroj použije aktivní konfigurace řešení.

- `/Project` *ProjName*

  Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat zobrazovaný název projektu nebo relativní cesta z *SolutionName* složku do souboru projektu. Můžete také zadat úplnou cestu a název souboru projektu.

- `/ProjectConfig` *ProjConfigName*

  Volitelné. Název konfigurace sestavení projektu (například `Debug` nebo `Release`) má být použit při čištění `/Project` s názvem. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud je tento přepínač zadaný, přepíše *Config* argument.

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

Tento přepínač provádí stejnou funkci jako **Vyčistit řešení** příkazu nabídky v rámci rozhraní IDE.

Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

Souhrnné informace při čištění a sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný [/Out](out-devenv-exe.md) přepnout.

Pokud `/Project` přepínač není zadán, čisticí akce se provádí na všechny projekty v řešení, i v případě *FileName* byl zadán jako soubor projektu.

## <a name="example"></a>Příklad

Vyčistí v prvním příkladu `MySolution` řešení pomocí výchozí konfigurace zadaná v souboru řešení.

V druhém příkladu vyčistí projektu `CSharpWinApp`, použije `Debug` konfigurace sestavení projektu v rámci `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /Clean

devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /Clean "Debug" /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)