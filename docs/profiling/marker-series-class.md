---
title: "marker_series – třída | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords: Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b326e88e18e3a7c5515cc11bfda7e5c35ae4a063
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="markerseries-class"></a>marker_series – třída
Představuje sériové kanál událostí generovaných jednoho zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class marker_series;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-constructors"></a>Veřejné konstruktory  
  
|Název|Popis|  
|----------|-----------------|  
|[marker_series::marker_series – konstruktor](../profiling/marker-series-marker-series-constructor.md)|Inicializuje novou instanci třídy `marker_series` třídy.|  
|[marker_series:: ~ marker_series – destruktor](../profiling/marker-series-tilde-marker-series-destructor.md)|Odstraní objekt marker_series a uvolní všechny přidělené prostředky.|  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[marker_series::is_enabled – metoda](../profiling/marker-series-is-enabled-method.md)|Určuje, zda má jakékoli relace povoleno zprostředkovatele.|  
|[marker_series::write_alert – metoda](../profiling/marker-series-write-alert-method.md)|Zapíše výstrahu vizualizér souběžnosti trasovacího souboru.|  
|[marker_series::write_flag – metoda](../profiling/marker-series-write-flag-method.md)|Zapíše příznak vizualizér souběžnosti trasovacího souboru.|  
|[marker_series::write_message – metoda](../profiling/marker-series-write-message-method.md)|Zapíše zprávu do Concurrency Visualizer trasovacího souboru.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchie dědičnosti  
 `marker_series`  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::Diagnostic –  
  
## <a name="see-also"></a>Viz také  
 [diagnostické Namespace](../profiling/diagnostic-namespace.md)