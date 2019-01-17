---
title: Iactivescriptprofilerheapenum – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 16756d0e-547a-4825-8b7b-a7e0e4708a04
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14562654e0fd3f3567d6f598f84cf2c966b1b8cb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344886"
---
# <a name="iactivescriptprofilerheapenum-interface"></a>IActiveScriptProfilerHeapEnum – rozhraní
Iterátor v haldě objekty spojených se skriptovacím modulem shromážděné [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
interface IActiveScriptProfilerHeapEnum : IUnknown  
```  
  
## <a name="methods"></a>Metody  
 [IActiveScriptProfilerHeapEnum::Next – metoda](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)  
 Získá další objekt nebo objekty v sadě objektů haldy shromážděné [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
 [IActiveScriptProfilerHeapEnum::GetOptionalInfo – metoda](../../winscript/reference/iactivescriptprofilerheapenum-getoptionalinfo-method.md)  
 Získá volitelné informace na zadaný objekt v sadě objektů haldy shromážděné [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
 [IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo – metoda](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)  
 Uvolní zadaný [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md) struktury a jejich přidružených [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md) elementy.  
  
 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)  
 Vrátí řetězcové názvy odpovídají [profiler_heap_object_name_id – typ](../../winscript/reference/profiler-heap-object-name-id-type.md) hodnoty...