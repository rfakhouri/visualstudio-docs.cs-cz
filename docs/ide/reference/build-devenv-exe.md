---
title: Přepínač nástroje DevEnv sestavení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: 777347ba36cf3443a509d1d6c8c44c23a86901e0
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764966"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

Sestavení řešení pomocí konfiguračního souboru zadaného řešení.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]
```

## <a name="arguments"></a>Arguments

|||
|-|-|
|*Název řešení SolutionName*|Požadováno. Úplná cesta a název souboru, řešení.|
|*SolnConfigName*|Požadováno. Název konfigurace řešení, který se použije k vytvoření řešení s názvem v *název řešení SolutionName*. Pokud jsou k dispozici více platforem řešení, musíte zadat také platformu, například **"ladění\|Win32"**.|
|/ project *ProjName*|Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z *název řešení SolutionName* složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.|
|/ projectconfig – *ProjConfigName*|Volitelné. Název projektu vytváření konfigurace má být použit při sestavení s názvem projektu. Pokud jsou k dispozici více platforem projekt, musíte zadat také platformu, například **"ladění\|Win32"**.|

## <a name="remarks"></a>Poznámky

- **/Build** přepínač provádí stejnou funkci jako **sestavit řešení** příkazu nabídky v rámci integrované vývojové prostředí (IDE).

- Uzavřete řetězců, které obsahují mezery v uvozovkách.

- Souhrnné informace o sestavení, včetně chyb, lze zobrazit v příkazovém okně nebo v jakékoli souboru protokolu zadaný **/out** přepínače.

- **/Build** přepínač pouze sestavení projektů, které se změnily od poslední sestavení. Chcete-li vytvořit všechny projekty v řešení, použijte [/rebuild](../../ide/reference/rebuild-devenv-exe.md) místo.

- Pokud se zobrazí chybová zpráva, která uvádí, že **konfigurací neplatný projektu**, ujistěte se, že jste určili platforma řešení nebo platformy projektu, například **"ladění\|Win32"**.

## <a name="example"></a>Příklad

Následující příkaz vytvoří projekt "CSharpConsoleApp" pomocí konfigurace sestavení projektu "Debug" v "Ladění" konfigurace řešení "MySolution".

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také:

- [Sestavení a vyčištění projektů a řešení](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Wwitches příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)