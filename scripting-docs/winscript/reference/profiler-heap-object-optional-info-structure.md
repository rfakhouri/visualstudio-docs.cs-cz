---
title: "Profiler_heap_object_optional_info – struktura | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 77e638bd-ae36-4292-a170-90a0c500e610
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 52e231484b48bf2741281644c746b448fd6f657b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectoptionalinfo-structure"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO – struktura
Volitelné informace o objektech halda představuje.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_OPTIONAL_INFO{    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE infoType;    [switch_type(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE), switch_is(infoType)] union    {        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE)] PROFILER_HEAP_OBJECT_ID prototype;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME)] LPCWSTR functionName;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE)] UINT elementAttributesSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE)] UINT elementTextChildrenSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST)] PROFILER_HEAP_OBJECT_SCOPE_LIST* scopeList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY)] PROFILER_HEAP_OBJECT_RELATIONSHIP* internalProperty;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* namePropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* indexPropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* relationshipList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* eventList;    };} PROFILER_HEAP_OBJECT_OPTIONAL_INFO;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Typ|Popis|  
|------------|----------|-----------------|  
|TypInfo|[PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE – výčet](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|Typ volitelné informace.|  
|prototyp|[Profiler_heap_object_id – typ](../../winscript/reference/profiler-heap-object-id-type.md)|ID objektu haldy prototyp objektu.|  
|%{FunctionName/|LPCWSTR|Název objektu haldy funkce.|  
|elementAttributesSize|UINT|Velikost objektu haldy element atributy.|  
|elementTextChildrenSize|UINT|Velikost objektu haldy text podřízené objekty.|  
|Seznam_oborů|[Profiler_heap_object_scope_list – struktura](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|Seznam objektu haldy oboru.|  
|internalProperty|[Profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md)|Interní vlastnost objektu haldy.|  
|namePropertyList|[Profiler_heap_object_relationship_list – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam vlastností objektu haldy název.|  
|indexPropertyList|[Profiler_heap_object_relationship_list – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam vlastností objektu haldy index.|  
|relationshipList|[Profiler_heap_object_relationship_list – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam objektu haldy vztahy.|  
|eventList|[Profiler_heap_object_relationship_list – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Seznam objektu haldy události.|