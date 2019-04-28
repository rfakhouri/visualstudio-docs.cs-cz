---
title: Profiler_heap_object_optional_info_type – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fcb55f5f-ce75-4d05-9ce9-ba28c622f97d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a56b05c572ec5d91914dd046bfdfa39224a07de
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823605"
---
# <a name="profilerheapobjectoptionalinfotype-enumeration"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE – výčet
Představuje různé druhy volitelných informací. Použít v [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE                    = 0x00000001,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME                = 0x00000002,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST                   = 0x00000003,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY            = 0x00000004,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES              = 0x00000005,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES             = 0x00000006,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE      = 0x00000007,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE   = 0x00000008,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS                = 0x00000009,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS                  = 0x0000000A,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE                    = PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS} PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE|0x00000001|Informace o objektu haldy prototypu.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME|0x00000002|Informace o objektu haldy název funkce.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST|0x00000003|Informace o objektu haldy [profiler_heap_object_scope_list – struktura](../../winscript/reference/profiler-heap-object-scope-list-structure.md).|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY|0x00000004|Informace o objektu haldy interní vlastnost.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES|0x00000005|Informace o objektu haldy název vlastnosti.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES|0x00000006|Informace o objektu haldy indexu vlastnosti.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE|0x00000007|Velikost atributy, které jsou spojeny s prvku modelu DOM.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE|0x00000008|Velikost jakýkoli text, který je přidružený k prvku modelu DOM.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS|0x00000009|Informace o relacích objekt haldy.|  
|ROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|0x0000000A|Informace o objektu haldy události prostředí Windows Runtime.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|Maximální hodnota tento výčet.|