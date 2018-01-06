---
title: -Znovu sestavit (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 957e987854aae91b72c5cd6109e279253a5772b1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
Vyčistí a potom vytvoří Zadaná konfigurace řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolnConfigName`  
 Požadováno. Název konfigurace řešení, který se použije k opětovnému sestavení řešení s názvem v `SolutionName`.  
  
 `SolutionName`  
 Požadováno. Úplná cesta a název souboru, řešení.  
  
 / Project`ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.  
  
 / projectconfig –`ProjConfigName`  
 Volitelné. Konfigurace, který se má použít při opětovném sestavování sestavení název projektu `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
  
-   Tento přepínač provádí stejnou funkci jako **znovu sestavit řešení** příkazu nabídky v rámci integrované vývojové prostředí (IDE).  
  
-   Uzavřete řetězců, které obsahují mezery v uvozovkách.  
  
-   Souhrnné informace o vyčistí a sestavení, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.  
  
## <a name="example"></a>Příklad  
 Tento příklad odstraní a znovu sestaví projekt `CSharpWinApp`pomocí `Debug` konfigurace sestavení projektu v rámci `Debug` konfiguraci řešení `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)