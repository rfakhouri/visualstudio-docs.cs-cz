---
title: -Runexit (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- runexit Devenv switch
- Devenv, /runexit switch
- /runexit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a8d91975fb56a8fd731a5998137a739ee364edf1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54793146"
---
# <a name="runexit-devenvexe"></a>/Runexit (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Zkompiluje a spustí zadaný projekt nebo řešení a potom jej zavře integrovaného vývojového prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /runexit {SolutionName|ProjectName}  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Povinný parametr. Úplná cesta a název souboru řešení.  
  
 `ProjectName`  
 Povinný parametr. Úplná cesta a název souboru projektu.  
  
## <a name="remarks"></a>Poznámky  
 Zkompiluje a spustí zadaný projekt nebo řešení podle nastavení nakonfigurovaného pro konfiguraci aktivního řešení. Tento přepínač minimalizuje rozhraní IDE při projekt nebo řešení je spustit a ho ukončí rozhraní IDE po projekt nebo řešení po dokončení jeho běhu.  
  
-   Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.  
  
-   Souhrnné informace, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/out` přepnout.  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí řešení `MySolution` v minimalizovaném okně integrovaného vývojového prostředí pomocí konfigurace aktivního nasazení a poté ukončí rozhraní IDE.  
  
```  
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Nebo spuštění (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
