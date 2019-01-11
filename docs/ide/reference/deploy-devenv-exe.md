---
title: -Deploy (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /Deploy switch
- Deploy Devenv switch
- deploying applications [Visual Studio], after build
- /Deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: efb8df01b69bd07a6e9169f690865c6ec2c9c104
ms.sourcegitcommit: 01185dadd2fa1f9a040d2a366869f1a5e1d18e0f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/11/2019
ms.locfileid: "54227626"
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)

Nasadí řešení po sestavení nebo opětovné sestavení. Platí pro pouze projekty spravovaného kódu.

## <a name="syntax"></a>Syntaxe

```shell
devenv SolutionName /Deploy [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Arguments

- *Název řešení*

  Povinný parametr. Úplná cesta a název souboru řešení.

- *SolnConfigName*

  Volitelné. Název konfigurace řešení, který se má použít k vytvoření řešení s názvem v *SolutionName*. Pokud tento argument je vynechána, nástroj použije aktivní konfigurace řešení.

- `/Project` *Název_projektu*

  Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat zobrazovaný název projektu nebo relativní cesta z *SolutionName* složku do souboru projektu. Můžete také zadat úplnou cestu a název souboru projektu.

- `/ProjectConfig` *ProjConfigName*

  Volitelné. Názvy projektu konfigurace se použije při sestavování sestavení `/Project` s názvem. Pokud je tento přepínač zadaný, přepíše *SolnConfigName* argument.

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

Zadaný projekt musí být projekt nasazení. Pokud zadaný projekt není projekt nasazení, když se pro nasazení projektu, který je sestavený Build, selže s chybou.

Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

Souhrnné informace o sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný [/Out](out-devenv-exe.md) přepnout.

## <a name="example"></a>Příklad

Tento příklad nasadí projekt `CSharpWinApp`, použije `Release` konfigurace sestavení projektu v rámci `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)