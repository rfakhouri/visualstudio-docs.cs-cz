---
title: marker_series – třída | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cb199d74ade593d0bc8318c27bc96ffbf70e4dcf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194930"
---
# <a name="markerseries-class"></a>marker_series – třída
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Představuje kanál sériového portu události generované modulem jednoho zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class marker_series;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-constructors"></a>Veřejné konstruktory  
  
|Name|Popis|  
|----------|-----------------|  
|[marker_series::marker_series – konstruktor](../profiling/marker-series-marker-series-constructor.md)|Inicializuje novou instanci třídy `marker_series` třídy.|  
|[marker_series::~marker_series – destruktor](../profiling/marker-series-tilde-marker-series-destructor.md)|Odstraní objekt marker_series – a uvolní všechny přidělené prostředky.|  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Name|Popis|  
|----------|-----------------|  
|[marker_series::is_enabled – metoda](../profiling/marker-series-is-enabled-method.md)|Určuje, zda všechny relace má povoleno zprostředkovatele.|  
|[marker_series::write_alert – metoda](../profiling/marker-series-write-alert-method.md)|Zapíše upozornění do souboru trasování vizualizátoru souběžnosti.|  
|[marker_series::write_flag – metoda](../profiling/marker-series-write-flag-method.md)|Příznak, který zapisuje do souboru trasování vizualizátoru souběžnosti.|  
|[marker_series::write_message – metoda](../profiling/marker-series-write-message-method.md)|Zapíše zprávu do souboru trasování vizualizátoru souběžnosti.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchie dědičnosti  
 `marker_series`  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::Diagnostic –  
  
## <a name="see-also"></a>Viz také  
 [diagnostic – obor názvů](../profiling/diagnostic-namespace.md)
