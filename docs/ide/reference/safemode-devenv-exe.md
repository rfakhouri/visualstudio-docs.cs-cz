---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c8748a6dadaee41a5e615742715a92240b74ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)