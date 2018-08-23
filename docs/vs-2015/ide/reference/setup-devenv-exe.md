---
title: -Setup (devenv.exe) | Dokumentace Microsoftu
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
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75b7fb7d812135014a8b868ef7590c99e83c15b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672469"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [– instalační program (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/setup-devenv-exe).  
  
  
Vynutí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sloučit resource metadata, která popisuje nabídky, panely nástrojů a příkaz skupin, ze všech dostupných rozšíření VSPackages.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač nepřijímá žádné argumenty. `devenv /setup` Příkaz je obvykle poskytnuta jako poslední krok z procesu instalace. Použití `/setup` přepínač nespustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 Je nutné spustit `devenv` jako správce, aby bylo možné používat [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) přepínače.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje poslední krok při instalaci verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , který obsahuje rozšíření VSPackages.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



