---
title: Aktivních skriptů Profiler konstanty, výčty a struktury | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6e079d84-9dde-46fc-8a6a-18e902f60ecc
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d39e6feb2cddd0c573368db9bf50b1e77f2e48d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955492"
---
# <a name="active-script-profiler-constants-enumerations-and-structures"></a>Konstanty, výčty a struktury profileru aktivních skriptů
Následující výčty jsou používány aktivní rozhraní Profiler skriptů.  
  
## <a name="constants-enumerations-and-structures"></a>Konstanty, výčty a struktury  
  
|Konstanty|Popis|  
|---------------|-----------------|  
|[PROFILER_EXTERNAL_OBJECT_ADDRESS – typ](../../winscript/reference/profiler-external-object-address-type.md)|Adresa externí objekt profileru. Použít v [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md) a [profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[PROFILER_HEAP_OBJECT_ID – typ](../../winscript/reference/profiler-heap-object-id-type.md)|ID objektu haldy. Použít v [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md)[profiler_heap_object_scope_list – struktura](../../winscript/reference/profiler-heap-object-scope-list-structure.md), [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md)a [Profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[PROFILER_HEAP_OBJECT_NAME_ID – typ](../../winscript/reference/profiler-heap-object-name-id-type.md)|ID názvu objektu haldy. Použít v [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md).|  
  
|Výčty|Popis|  
|------------------|-----------------|  
|[PROFILER_EVENT_MASK – výčet](../../winscript/reference/profiler-event-mask-enumeration.md)|Určuje typy událostí, které by se dalo Profilovat.|  
|[PROFILER_HEAP_ENUM_FLAGS – výčet](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)|Příznak, který označuje, zda je přístupný dodatečné informace o objektu haldy, na který je odkazováno v objektovém vztahu. Používáno [iactivescriptprofilercontrol5::enumheap2 – metoda](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md).|  
|[PROFILER_HEAP_OBJECT_FLAGS – výčet](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|Příznaky, které představují základní informace o objektu haldy. Používáno [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md).|  
|[PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE – výčet](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|Představuje různé druhy volitelných informací. Použít v [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md).|  
|[PROFILER_RELATIONSHIP_INFO – výčet](../../winscript/reference/profiler-relationship-info-enumeration.md)|Představuje informace o objektu ve vztahu. Použít v [profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md).|  
|[PROFILER_SCRIPT_TYPE – výčet](../../winscript/reference/profiler-script-type-enumeration.md)|Určuje typ skriptu.|  
  
|Struktury|Popis|  
|----------------|-----------------|  
|[PROFILER_HEAP_OBJECT – struktura](../../winscript/reference/profiler-heap-object-structure.md)|Shromážděné objekty halda představuje [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).|  
|[PROFILER_HEAP_OBJECT_OPTIONAL_INFO – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md)|Představuje volitelných informací o objektech v haldě.|  
|[PROFILER_HEAP_OBJECT_RELATIONSHIP – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md)|Představuje vztah objektu haldy.|  
|[PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST – struktura](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Představuje seznam vztahy, které patří do objektu haldy.|  
|[PROFILER_HEAP_OBJECT_SCOPE_LIST – struktura](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|Tato struktura je přidružený jenom objekty funkce. Seznam oborů představuje uzavření pro funkci jako seznam oborů, kde každý obor je objekt haldy se seznamem přidružené vlastnosti, která představuje proměnné v každé daném oboru. V některých případech se názvy objektů v tomto oboru nemusí být k dispozici, pouze jejich ID.|  
|[PROFILER_PROPERTY_TYPE_SUBSTRING_INFO – struktura](../../winscript/reference/profiler-property-type-substring-info-structure.md)|Představuje informace o typu dílčí řetězec.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)