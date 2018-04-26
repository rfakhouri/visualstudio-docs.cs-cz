---
title: -Sestavení (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 90e331ed637edcc81dc99f99c3ec39aa75928f7d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)
Sestavení řešení pomocí konfiguračního souboru zadaného řešení.

## <a name="syntax"></a>Syntaxe

```
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]
```

## <a name="arguments"></a>Arguments
 `SolutionName` Vyžaduje se. Úplná cesta a název souboru, řešení.

 `SolnConfigName` Vyžaduje se. Název konfigurace řešení, který se použije k vytvoření řešení s názvem v `SolutionName`.

 / project `ProjName` volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.

 / projectconfig – `ProjConfigName` volitelné. Konfigurace, který se má použít při vytváření sestavení název projektu `/project` s názvem.

## <a name="remarks"></a>Poznámky
 Tento přepínač provádí stejnou funkci jako **sestavit řešení** příkazu nabídky v rámci integrované vývojové prostředí (IDE).

 Uzavřete řetězců, které obsahují mezery v uvozovkách.

 Souhrnné informace o sestavení, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.

 Tento příkaz vytvoří pouze projekty, které se změnily od poslední sestavení. Chcete-li vytvořit všechny projekty v řešení, použijte [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md).

## <a name="example"></a>Příklad
 Tento příklad vytvoří projekt `CSharpConsoleApp`pomocí `Debug` konfigurace sestavení projektu v rámci `Debug` konfiguraci řešení `MySolution`.

```
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také

- [Sestavování a čištění projektů a řešení v sadě Visual Studio](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)