---
title: Profiler_heap_enum_flags – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 17936b7a-40d5-4774-b92b-b24ee391591e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d613ed3bcb4699f20d521f08b6c34d55d8363ba4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62830354"
---
# <a name="profilerheapenumflags-enumeration"></a>PROFILER_HEAP_ENUM_FLAGS – výčet
Příznak, který označuje, zda je přístupný dodatečné informace o objektu haldy, na který je odkazováno v objektovém vztahu. Používáno [EnumHeap2](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef [v1_enum] enum {    PROFILER_HEAP_ENUM_FLAGS_NONE                      = 0x00000000,    PROFILER_HEAP_ENUM_FLAGS_STORE_RELATIONSHIP_FLAGS  = 0x00000001,} PROFILER_HEAP_ENUM_FLAGS;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_ENUM_FLAGS_NONE|0x00000000|Tento objekt haldy nemůže vystavovat další informace o vztahu objektu. Tento objekt haldy se chová stejně jako [IActiveScriptProfilerControl3::HeapEnum](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).|  
|PROFILER_HEAP_ENUM_ENUM_ STORE_RELATIONSHIP_FLAGS|0x00000001|Tento objekt haldy bude vystavovat informace o tom, zda je objekt, na který je odkazováno v objektovém vztahu, metoda getter nebo setter. Tyto informace budou uloženy ve výšce 2 bajtů (16 bitů) z [PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo](../../winscript/reference/profiler-heap-object-relationship-structure.md) pole jako jeden z [profiler_heap_object_relationship_flags –](../../winscript/reference/profiler-heap-object-relationship-flags-enumeration.md) hodnoty výčtu.|  
|PROFILER_HEAP_ENUM_FLAGS_SUBSTRINGS|0x00000002|Tento objekt haldy se používá k zobrazení podřetězec správně.|  
|PROFILER_HEAP_ENUM_FLAGS_RELATIONSHIP_SUBSTRINGS|PROFILER_HEAP_ENUM_FLAGS_STORE_RELATIONSHIP_FLAGS &AMP;#124; PROFILER_HEAP_ENUM_FLAGS_SUBSTRINGS|Tento objekt haldy se používá k zobrazení podřetězec správně.|