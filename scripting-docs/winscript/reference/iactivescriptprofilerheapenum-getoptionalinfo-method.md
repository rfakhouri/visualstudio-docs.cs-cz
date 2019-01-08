---
title: Iactivescriptprofilerheapenum::getoptionalinfo – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcba1214a0c57e738dec41cdc4976f478802fedc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088800"
---
# <a name="iactivescriptprofilerheapenumgetoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::GetOptionalInfo – metoda
Získá volitelné informace na zadaný objekt (ze sady vrácených z objektů haldy [iactivescriptprofilercontrol3::enumheap – metoda](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)).  
  
 Nesmí uvolnit vrácené paměť přiřazená vrácených objektů. Místo toho byste měli volat [iactivescriptprofilerheapenum::freeobjectandoptionalinfo – metoda](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetOptionalInfo (    [in] PROFILER_HEAP_OBJECT* heapObject,    [in] ULONG celt,    [out, size_is(celt)] PROFILER_HEAP_OBJECT_OPTIONAL_INFO* optionalInfo);  
```  
  
#### <a name="parameters"></a>Parametry  
 `heapObject`  
 [Profiler_heap_object – struktura](../../winscript/reference/profiler-heap-object-structure.md) pro které se mají vracet informace.  
  
 `celt`  
 Počet [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md) struktury vrácení.  
  
 `optionalInfo`  
 [out] Pole [profiler_heap_object_optional_info – struktura](../../winscript/reference/profiler-heap-object-optional-info-structure.md) struktury pro zadaný objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT.