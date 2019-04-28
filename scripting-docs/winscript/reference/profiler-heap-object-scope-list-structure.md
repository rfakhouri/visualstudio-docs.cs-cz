---
title: Profiler_heap_object_scope_list – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 33ebaa31-0a35-47d5-a4e3-afd83e16f53e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1285e4efa3db8a7ec99808f5888d3dbf948e589
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62830318"
---
# <a name="profilerheapobjectscopelist-structure"></a>PROFILER_HEAP_OBJECT_SCOPE_LIST – struktura
Tato struktura je přidružený jenom objekty funkce. Seznam oborů představuje uzavření pro funkci jako seznam oborů, kde každý obor je objekt haldy se seznamem přidružené vlastnosti, která představuje proměnné v každé daném oboru. V některých případech se názvy objektů v oboru nebudou k dispozici a jejich se budou indexovat jen do seznamu vlastností je k dispozici.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_SCOPE_LIST{    UINT count;    [size_is(count)] PROFILER_HEAP_OBJECT_ID scopes[];} PROFILER_HEAP_OBJECT_SCOPE_LIST;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Type|Popis|  
|------------|----------|-----------------|  
|count|UINT|Počet rozsahů|  
|scopes|[PROFILER_HEAP_OBJECT_ID – typ](../../winscript/reference/profiler-heap-object-id-type.md)|Celou řadu oborů.|