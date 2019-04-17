---
title: -Setup (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6e5bbbf3a1a9601a46aa9d3080f0d20583b43d22
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670235"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
