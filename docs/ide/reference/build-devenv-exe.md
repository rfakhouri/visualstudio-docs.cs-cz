---
title: "-Sestavení (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 490c3c4f424d9a8bac2fb0d4042604f8a53439fe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)
Sestavení řešení pomocí konfiguračního souboru zadaného řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Požadováno. Úplná cesta a název souboru, řešení.  
  
 `SolnConfigName`  
 Požadováno. Název konfigurace řešení, který se použije k vytvoření řešení s názvem v `SolutionName`.  
  
 / Project`ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.  
  
 / projectconfig –`ProjConfigName`  
 Volitelné. Konfigurace, který se má použít při vytváření sestavení název projektu `/project` s názvem.  
  
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
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)