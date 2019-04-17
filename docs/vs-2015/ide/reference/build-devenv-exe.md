---
title: -Sestavení (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4c6f5f80512371ae323fbbfe143eb98bffbe7d98
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59668363"
---
# <a name="build-devenvexe"></a>/ Sestavení (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Sestavení řešení je používán konfigurační soubor zadaného řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Povinný parametr. Úplná cesta a název souboru řešení.  
  
 `SolnConfigName`  
 Povinný parametr. Název konfigurace řešení, která se použije k vytvoření řešení s názvem v `SolutionName`.  
  
 / Project `ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.  
  
 /projectconfig `ProjConfigName`  
 Volitelné. Název projektu konfigurace se použije při sestavování sestavení `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač provádí stejnou funkci jako **sestavit řešení** příkazu nabídky v rámci integrovaného vývojového prostředí (IDE).  
  
 Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.  
  
 Souhrnné informace o sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/out` přepnout.  
  
 Tento příkaz sestaví pouze projekty, které se změnily od posledního sestavení. Chcete-li sestavit všechny projekty v řešení, použijte [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md).  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří projekt `CSharpConsoleApp`, použije `Debug` konfigurace sestavení projektu v rámci `Debug` konfigurace řešení `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Viz také  
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
