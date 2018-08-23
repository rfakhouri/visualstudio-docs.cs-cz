---
title: -ResetSkipPkgs (devenv.exe) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e03e260662330556bff8f15a83fe747c374154b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676298"
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [- ResetSkipPkgs (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/resetskippkgs-devenv-exe).  
  
  
Vymaže všechny možnosti, chcete-li přeskočit načítání přidané do balíků VSPackages uživatelé chtějí předejít problém rozšíření VSPackages a pak spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## <a name="remarks"></a>Poznámky  
 Přítomnost značky SkipLoading zakáže načítání VSPackage; vymazává se značka znovu povolí načítání sady VSPackage.  
  
## <a name="example"></a>Příklad  
 Následující příklad odebere všechny značky SkipLoading.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



