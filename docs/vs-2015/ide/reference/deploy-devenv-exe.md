---
title: -Nasazení (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0dac8564c06efd65b8db04e0aa0fae97a849e6cb
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59658081"
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nasadí řešení po sestavení nebo opětovné sestavení. Platí pro pouze projekty spravovaného kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolnConfigName`  
 Povinný parametr. Název konfigurace řešení, která se použije k vytvoření řešení s názvem v `SolutionName`.  
  
 `SolutionName`  
 Povinný parametr. Úplná cesta a název souboru řešení.  
  
 / Project `ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.  
  
 /projectconfig `ProjConfigName`  
 Volitelné. Název projektu konfigurace se použije při sestavování sestavení `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
 Zadaný projekt musí být projekt nasazení. Pokud zadaný projekt není projekt nasazení, pokud projekt, který je sestavený Build je předán do nasazení, selže s chybou.  
  
 Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.  
  
 Souhrnné informace o sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/out` přepnout.  
  
## <a name="example"></a>Příklad  
 Tento příklad nasadí projekt `CSharpConsoleApp`, použije `Release` konfigurace sestavení projektu v rámci `Release` konfigurace řešení `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
