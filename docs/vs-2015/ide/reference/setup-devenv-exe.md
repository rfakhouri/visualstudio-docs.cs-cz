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
ms.openlocfilehash: 0df3b74b6c5acc4b8630dcf5759dd3fd6e7a1afe
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805362"
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
