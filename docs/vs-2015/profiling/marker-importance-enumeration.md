---
title: marker_importance – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_importance
helpviewer_keywords:
- Concurrency::diagnostic::marker_importance enumeration
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 853b31ddec99587c9c649e3ee10d77a6f4b4803e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49179449"
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
  
 **Namespace:** Concurrency::Diagnostic –  
  
## <a name="see-also"></a>Viz také  
 [diagnostic – obor názvů](../profiling/diagnostic-namespace.md)



