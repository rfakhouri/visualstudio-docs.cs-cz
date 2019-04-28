---
title: Profiler_heap_object_relationship_flags – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1a41b642-c9a9-4d83-b943-d59b232eebf6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 322f6f3352c1b0dfad4572d55e1ebe2388c8cc4a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823631"
---
# <a name="profilerheapobjectrelationshipflags-enumeration"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS – výčet
Příznaky, které označuje, zda objekt haldy ukazoval na vztahu k objektu představuje metodu getter nebo setter. Používané [EnumHeap2](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md) metodu, pokud je zadána hodnota PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS v `enumFlags` parametru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_NONE                      = 0x00000000,    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_GET_ACCESSOR           = 0x00010000,    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_SET_ACCESSOR           = 0x00020000,} PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_NONE|0x00000000|Tento objekt haldy, na který je odkazováno v objektovém vztahu není označen jako metoda getter nebo setter.|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_GET_ACCESSOR|0x00010000|Objekt haldy, na který je odkazováno v objektovém vztahu je metodu getter. Tyto informace budou uloženy ve výšce 2 bajtů (16 bitů) z [PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo](../../winscript/reference/profiler-heap-object-relationship-structure.md) pole.|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_SET_ACCESSOR|0x00020000|Objekt haldy, na který je odkazováno v objektovém vztahu je metodu setter. Tyto informace budou uloženy ve výšce 2 bajtů (16 bitů) z `PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo` pole.|