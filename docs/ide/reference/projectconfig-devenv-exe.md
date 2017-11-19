---
title: -ProjectConfig (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 954d2807e510e43e0931070335dce5f92d5c2464
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)
Určuje, který bude použit při sestavení, vyčistit, znovu sestavit nebo nasazení projektu s názvem v konfigurace sestavení projektu `/project` argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>Arguments  
 / Build  
 Sestavení projektu určeného `/project` `ProjName`.  
  
 / clean  
 Odstraní všechny zprostředkující soubory a adresáře výstup vytvořené během sestavení.  
  
 / rebuild  
 Vyčistí pak sestavení projektu určeného `/project` `ProjName`.  
  
 / nasazení  
 Určuje, že projekt nasazen po sestavení nebo opětovném sestavení.  
  
 `SolnConfigName`  
 Požadováno. Název konfigurace řešení, které se použijí k řešení s názvem v `SolutionName`.  
  
 `SolutionName`  
 Požadováno. Úplná cesta a název souboru, řešení.  
  
 / Project`ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku pro soubor projektu nebo projektu zobrazovaný název, nebo úplnou cestu a název souboru projektu.  
  
 / projectconfig –`ProjConfigName`  
 Volitelné. Konfigurace, které má být použita pro sestavení název projektu `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
  
-   Musí být použit s `/project` přepínače v rámci `devenv /build`, nebo`clean`, `/rebuild`, nebo `/deploy` příkaz.  
  
-   Uzavřete řetězců, které obsahují mezery v uvozovkách.  
  
-   Souhrnné informace o sestavení, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří projekt `CSharpConsoleApp`pomocí `Debug` konfigurace sestavení projektu v rámci `Debug` konfiguraci řešení `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Nasadit (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)