---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 72630bd7c16c3830fecddc34a71b7ea1e4cf382c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu, načítání výchozí prostředí a služeb.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač zabrání všechny VSPackages třetích stran při načítání [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí, čímž zajišťuje stabilní provádění.  
  
## <a name="description"></a>Popis  
 Následující příklad spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu.  
  
## <a name="code"></a>Kód  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)