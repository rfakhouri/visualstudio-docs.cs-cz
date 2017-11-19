---
title: -Spustit (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /run Devenv
- run Devenv switch
- applications [Visual Studio], running
- /r Devenv switch
- Devenv, /run switch
- r Devenv switch (/r)
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5be97e75ac7dc29a6dd0244293259bcd17591233
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="run-devenvexe"></a>/Run (devenv.exe)
Zkompiluje a spustí na zadaný projekt nebo řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv {/run|/r} {SolutionName|ProjectName}  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Požadováno. Úplná cesta a název souboru, řešení.  
  
 `ProjectName`  
 Požadováno. Úplná cesta a název souboru projektu.  
  
## <a name="remarks"></a>Poznámky  
 Zkompiluje a spustí na zadaný projekt nebo řešení podle nastavení zadaných pro konfiguraci aktivním řešení. Tento přepínač spustí integrované vývojové prostředí (IDE) a zůstane aktivní po projekt nebo řešení dokončení běhu.  
  
-   Uzavřete řetězců, které obsahují mezery v uvozovkách.  
  
-   Souhrnné informace, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí řešení `MySolution` pomocí konfigurace aktivní nasazení.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)