---
title: Profiler_heap_object_relationship – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3ab3d986-3314-4c7b-a1c8-18ed691a8b9c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a905a44f2ef686181c5a859699277d16f6cd374
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823618"
---
# <a name="profilerheapobjectrelationship-structure"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP – struktura
Představuje vztah objektu haldy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP{    PROFILER_HEAP_OBJECT_NAME_ID relationshipId;    PROFILER_RELATIONSHIP_INFO relationshipInfo;    [switch_type(PROFILER_RELATIONSHIP_INFO), switch_is(relationshipInfo)] union    {        [case(PROFILER_PROPERTY_TYPE_NUMBER)] double numberValue;        [case(PROFILER_PROPERTY_TYPE_STRING)] LPCWSTR stringValue;        [case(PROFILER_PROPERTY_TYPE_HEAP_OBJECT)] PROFILER_HEAP_OBJECT_ID objectId;        [case(PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT)] PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };} PROFILER_HEAP_OBJECT_RELATIONSHIP;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Hodnota|Popis|  
|------------|-----------|-----------------|  
|relationshipId|[PROFILER_HEAP_OBJECT_NAME_ID – typ](../../winscript/reference/profiler-heap-object-name-id-type.md)|ID relace název z [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md).|  
|relationshipInfo|[PROFILER_RELATIONSHIP_INFO – výčet](../../winscript/reference/profiler-relationship-info-enumeration.md)|Informace o vztahu.|  
|numberValue|double|Číselná hodnota. Pouze jeden z `numberValue` / `stringValue` / `objectId` / `externalObjectAddress` je nastavena, na základě `relationshipInfo` hodnotu.|  
|stringValue|LPCWSTR|Hodnota řetězce.|  
|ID objektu|[PROFILER_HEAP_OBJECT_ID – typ](../../winscript/reference/profiler-heap-object-id-type.md)|ID objektu haldy.|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS – typ](../../winscript/reference/profiler-external-object-address-type.md)|Adresu externího objektu.|  
|dílčí řetězec|[PROFILER_PROPERTY_TYPE_SUBSTRING_INFO – struktura](../../winscript/reference/profiler-property-type-substring-info-structure.md)|Informace o typu dílčí řetězec.|