---
title: Iactivescriptprofilerheapenum::freeobjectandoptionalinfo – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fdd5f7cc-be4e-4c13-a181-6320d26b44eb
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6023ca95b3e861b7bf57db3d37c7949e650419b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992884"
---
# <a name="iactivescriptprofilerheapenumfreeobjectandoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo – metoda
Uvolní zadaný [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md) struktury a jejich přidružených [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md) elementy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT FreeObjectAndOptionalInfo (    [in] ULONG celt,    [in, size_is(celt)] PROFILER_HEAP_OBJECT** heapObjects);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 Počet objektů pro uvolnění.  
  
 `heapObjects`  
 Pole [profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md) struktury.  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT.