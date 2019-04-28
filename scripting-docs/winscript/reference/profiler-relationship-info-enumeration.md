---
title: Profiler_relationship_info – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fae69317-6224-4a6a-8e9e-ccaa6a330818
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0aa0a94668d06f75b959de2ee933ab079feba596
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808890"
---
# <a name="profilerrelationshipinfo-enumeration"></a>PROFILER_RELATIONSHIP_INFO – výčet
Představuje informace o objektu ve vztahu. Použít v [profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef [v1_enum] enum {    PROFILER_PROPERTY_TYPE_NUMBER = 0x01,    PROFILER_PROPERTY_TYPE_STRING = 0x02,    PROFILER_PROPERTY_TYPE_HEAP_OBJECT = 0x03,    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT = 0x04,    PROFILER_PROPERTY_TYPE_BSTR = 0x05,} PROFILER_RELATIONSHIP_INFO;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Value|Popis|  
|------------|-----------|-----------------|  
|PROFILER_PROPERTY_TYPE_NUMBER|0x01|Objekt je číslo.|  
|PROFILER_PROPERTY_TYPE_STRING|0x02|Objekt je řetězec.|  
|PROFILER_PROPERTY_TYPE_HEAP_OBJECT|0x03|Objekt je objekt haldy.|  
|PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT|0x04|Objekt není externí, tedy na haldě uvolňování paměti.|  
|PROFILER_PROPERTY_TYPE_BSTR|0x05|Objekt je BSTR.|  
|PROFILER_PROPERTY_TYPE_SUBSTRING|0x06|Objekt je dílčí řetězec.|