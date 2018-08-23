---
title: -Nouzový režim (devenv.exe) | Dokumentace Microsoftu
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
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 308dd7e81a35604bcd0f6f5eba517b850ace17ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671975"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [- Nouzový režim (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/safemode-devenv-exe).  
  
  
Spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] v nouzovém režimu, načítání výchozí prostředí a služeb.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>Poznámky  
 Při načítání rozšíření VSPackages všechny třetích stran zabraňuje tento přepínač [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] se spustí, čímž zajišťuje stabilní spuštění.  
  
## <a name="description"></a>Popis  
 Následující příklad spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] v nouzovém režimu.  
  
## <a name="code"></a>Kód  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)



