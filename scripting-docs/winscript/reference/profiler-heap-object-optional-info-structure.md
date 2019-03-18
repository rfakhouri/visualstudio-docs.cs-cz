---
title: Profiler_heap_object_optional_info – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 77e638bd-ae36-4292-a170-90a0c500e610
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c7f28499b5d6e1e01caab1e6fd83fc5ab72ccf6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58151034"
---
# <a name="profilerheapobjectoptionalinfo-structure"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO – struktura
Představuje volitelných informací o objektech v haldě.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_OPTIONAL_INFO{    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE infoType;    [switch_type(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE), switch_is(infoType)] union    {        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE)] PROFILER_HEAP_OBJECT_ID prototype;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME)] LPCWSTR functionName;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE)] UINT elementAttributesSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE)] UINT elementTextChildrenSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST)] PROFILER_HEAP_OBJECT_SCOPE_LIST* scopeList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY)] PROFILER_HEAP_OBJECT_RELATIONSHIP* internalProperty;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* namePropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* indexPropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* relationshipList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* eventList;    };} PROFILER_HEAP_OBJECT_OPTIONAL_INFO;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Typ|Popis|  
|------------|----------|-----------------|  
|infoType|[PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE – výčet](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|Typ volitelných informací.|  
|prototyp|[PROFILER_HEAP_OBJECT_ID – typ](../../winscript/reference/profiler-heap-object-id-type.md)|ID objektu prototypu objektu haldy.|  
|functionName|LPCWSTR|Název funkce objekt haldy.|  
|elementAttributesSize|UINT|Velikost atributy prvků objekt haldy.|  
|elementTextChildrenSize|UINT|Velikost podřízené objekty textový objekt haldy.|  
|Seznam_oborů|[PROFILER_HEAP_OBJECT_SCOPE_LIST – struktura](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|Seznam oborů objekt haldy.|  
|internalProperty|[PROFILER_HEAP_OBJECT_RELATIONSHIP – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md)|Interní vlastnost objekt haldy.|  
|namePropertyList|[PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam vlastností název objektu haldy.|  
|indexPropertyList|[PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam vlastností objektu haldy indexu.|  
|relationshipList|[PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam relací objekt haldy.|  
|eventList|[PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam událostí objekt haldy.|