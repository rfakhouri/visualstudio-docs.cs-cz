---
title: marker_importance – výčet | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords:
- Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a4451a7b222b66f0fe5bea2b0e5f2b8499c9033c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779034"
---
# <a name="markerimportance-enumeration"></a>marker_importance – výčet
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Představuje úroveň důležitosti značek Vizualizátor souběžnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum marker_importance;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`critical_importance`|Určuje, že má značku stěžejní význam.|  
|`high_importance`|Určuje, že značky má vysokou důležitostí.|  
|`low_importance`|Určuje, zda má značku s nízkou důležitostí.|  
|`normal_importance`|Určuje, že značky má normální význam.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Viz také  
 [diagnostic – obor názvů](../profiling/diagnostic-namespace.md)
