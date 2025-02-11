---
title: -ProjectConfig (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
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
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4b956fb09681f6f4a1f916f4b108028f69f009cd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200903"
---
# <a name="projectconfig-devenvexe"></a>/ ProjectConfig (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje konfiguraci sestavení projektu, kterou chcete použít při sestavení, vyčištění, znovu sestavit nebo nasadit projekt s názvem v `/project` argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>Arguments  
 / Build  
 Vytvoří projekt určený `/project` `ProjName`.  
  
 / clean  
 Vyčistí všechny zprostředkující soubory a výstupní adresáře, které jsou vytvořeny během sestavení.  
  
 / rebuild  
 Vyčistí pak vytvoří projekt určený `/project` `ProjName`.  
  
 / deploy  
 Určuje, že projekt nasadit po sestavení nebo opětovné sestavení.  
  
 `SolnConfigName`  
 Povinný parametr. Název konfigurace řešení, která se použije k řešení s názvem v `SolutionName`.  
  
 `SolutionName`  
 Povinný parametr. Úplná cesta a název souboru řešení.  
  
 / Project `ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.  
  
 / projectconfig `ProjConfigName`  
 Volitelné. Název projektu konfigurace použít k sestavení `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
  
- Je nutné použít s `/project` přepnout jako součást `devenv /build`, /`clean`, `/rebuild`, nebo `/deploy` příkazu.  
  
- Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.  
  
- Souhrnné informace o sestavení, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/out` přepnout.  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří projekt `CSharpConsoleApp`, použije `Debug` konfigurace sestavení projektu v rámci `Debug` konfigurace řešení `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
