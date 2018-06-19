---
title: -Nasazení (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 368680321f8ff8ab908e79e075a5797ba9ecd598
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945113"
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
Nasadí řešení po sestavení nebo opětovném sestavení. Týká jenom projektů spravovaného kódu.

## <a name="syntax"></a>Syntaxe

```
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]
```

## <a name="arguments"></a>Arguments
 `SolnConfigName`

 Požadováno. Název konfigurace řešení, který se použije k vytvoření řešení s názvem v `SolutionName`.

 `SolutionName`

 Požadováno. Úplná cesta a název souboru, řešení.

 / Project `ProjName`

 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.

 / projectconfig – `ProjConfigName`

 Volitelné. Konfigurace, který se má použít při vytváření sestavení název projektu `/project` s názvem.

## <a name="remarks"></a>Poznámky
 Projekt nasazení musí být zadaný projekt. Pokud zadaný projekt není projekt nasazení, když na projekt, který je sestavený předána nasadit, se nezdaří s chybou.

 Uzavřete řetězců, které obsahují mezery v uvozovkách.

 Souhrnné informace o sestavení, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.

## <a name="example"></a>Příklad
 Tento příklad nasadí projekt `CSharpConsoleApp`pomocí `Release` konfigurace sestavení projektu v rámci `Release` konfiguraci řešení `MySolution`.

```
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)