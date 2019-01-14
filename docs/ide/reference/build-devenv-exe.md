---
title: -Build (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- builds, command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
- command-line builds
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30637a797d8c0845bae9548bb6a48e877d44727b
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269472"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

Sestaví řešení nebo projekt je používán konfigurační soubor zadaného řešení.

## <a name="syntax"></a>Syntaxe

```shell
devenv SolutionName /Build [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Povinný parametr. Úplná cesta a název souboru řešení.

- *SolnConfigName*

  Volitelné. Název konfigurace řešení (například `Debug` nebo `Release`) se použije k vytvoření řešení s názvem v *SolutionName*. Pokud jsou k dispozici více platformy řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud tento argument není zadána nebo prázdný řetězec (`""`), nástroj použije aktivní konfigurace řešení.

- `/Project` *ProjName*

  Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z *SolutionName* složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.

- `/ProjectConfig` *ProjConfigName*

  Volitelné. Konfigurace sestavení název projektu (například `Debug` nebo `Release`) má být použit při sestavení s názvem projektu. Pokud je k dispozici více než jedné platformě řešení, musíte zadat také platformy (například `Debug|Win32`). Pokud je tento přepínač zadaný, přepíše *SolnConfigName* argument.

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

- `/Build` Přepínač provádí stejnou funkci jako **sestavit řešení** příkazu nabídky v rámci integrovaného vývojového prostředí (IDE).

- Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

- Souhrnné informace o sestavení, včetně chyb, lze zobrazit, v příkazovém okně nebo do jakéhokoli souboru protokolu zadaný `/Out` přepnout.

- `/Build` Přepínač sestavuje pouze projekty, které se změnily od posledního sestavení. Chcete-li sestavit všechny projekty v řešení, použijte [/rebuild](../../ide/reference/rebuild-devenv-exe.md) místo.

- Pokud se zobrazí chybová zpráva s upozorněním **neplatná konfigurace projektu**, ujistěte se, že jste zadali platforma řešení nebo projektu platformy (například `Debug|Win32`).

## <a name="example"></a>Příklad

Následující příkaz sestaví projekt `CSharpWinApp`, použije `Debug` konfigurace sestavení projektu v rámci `MySolution`.

```shell
devenv "%USERPROFILE%\source\repos\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také:

- [Sestavení a vyčištění projektů a řešení](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)