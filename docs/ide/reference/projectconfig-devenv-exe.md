---
title: Přepínač nástroje DevEnv ProjectConfig
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /projectconfig Devenv switch
- configurations, rebuilding
- deployment projects, creating
- configurations, cleaning
- deployment projects, specifying
- deployment projects, adding
- build configurations, specifying
- Devenv, /projectconfig switch
- projectconfig Devenv switch (/projectconfig)
- projects [Visual Studio], build configuration
- projects [Visual Studio], cleaning
ms.assetid: 6b54ef59-ffed-4f62-a645-1279ede97ebf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7ca481d23757cc9022042db42a6d4be477880367
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967914"
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)

Určuje konfiguraci sestavení projektu, kterou chcete použít při sestavení, vyčištění, znovu sestavit nebo nasadit projekt s názvem v **/project** argument.

## <a name="syntax"></a>Syntaxe

```cmd
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Arguments

|||
|-|-|
|/ Build|Vytvoří projekt určený **/project** argument.|
|/ clean|Vyčistí všechny zprostředkující soubory a výstupní adresáře, které jsou vytvořeny během sestavení.|
|/ rebuild|Vyčistí pak vytvoří projekt určený **/project** argument.|
|/ deploy|Určuje, že projekt nasadit po sestavení nebo opětovné sestavení.|
|*SolnConfigName*|Povinný parametr. Název konfigurace řešení, která se použije k řešení s názvem v *SolutionName*. Pokud jsou k dispozici více platformy řešení, musíte zadat také platformu, například **"ladění\|Win32"**.|
|*Název řešení*|Povinný parametr. Úplná cesta a název souboru řešení.|
|/ project *název_projektu*|Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z *SolutionName* složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.|
|/ projectconfig *ProjConfigName*|Volitelné. Název projektu sestavení konfigurace použít projekt určený **/project** argument. Pokud jsou k dispozici více platformy řešení, musíte zadat také platformu, například **"ladění\|Win32"**.|

## <a name="remarks"></a>Poznámky

**/Projectconfig** přepínač musí použít společně s **/project** přepnout jako součást **/build**, **/ clean**,  **/rebuild**, nebo **/ deploy** příkazu.

Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

Souhrnné informace o sestavení, včetně chyb, lze zobrazit, v příkazovém okně nebo do jakéhokoli souboru protokolu zadaný **/out** přepnout.

## <a name="example"></a>Příklad

Následující příkaz sestaví projekt "CSharpConsoleApp", "Ladění" konfigurace sestavení projektu v rámci konfigurace "Debug" řešení "MySolution" pomocí:

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)