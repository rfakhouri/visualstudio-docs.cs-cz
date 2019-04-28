---
title: Profiler_heap_object – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9f35362c-6856-4cfb-b990-031a156a58eb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1652c6ebffff88782ffcc879158a5142f22395d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823811"
---
# <a name="profilerheapobject-structure"></a>PROFILER_HEAP_OBJECT – struktura
Shromážděné objekty halda představuje [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT  
{  
    UINT size;    union {        PROFILER_HEAP_OBJECT_ID objectId;        PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };    PROFILER_HEAP_OBJECT_NAME_ID typeNameId;    USHORT flags;     USHORT optionalInfoCount;} PROFILER_HEAP_OBJECT;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Type|Popis|  
|------------|----------|-----------------|  
|ID objektu|[PROFILER_HEAP_OBJECT_ID – typ](../../winscript/reference/profiler-heap-object-id-type.md)|ID objektu haldy.|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS – typ](../../winscript/reference/profiler-external-object-address-type.md)|Adresa externí objekt objektu, například objekt přidělený C++, mimo haldu využívanou jazykem JavaScript.|  
|typeNameId|[PROFILER_HEAP_OBJECT_NAME_ID – typ](../../winscript/reference/profiler-heap-object-name-id-type.md)|Načetlo se ID názvu typu objektu haldy, z [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md). Pouze jeden z `externalObjectAddress` nebo `typeName` je k dispozici v závislosti na tom `flags` hodnotu.|  
|příznaky|[PROFILER_HEAP_OBJECT_FLAGS – výčet](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|Příznaky, které obsahují základní informace o objektu haldy.|  
|optionalInfoCount|USHORT|Počet [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md) záznamy, které jsou k dispozici pro objekt haldy.|