---
title: Iactivescriptprofilerheapenum::getoptionalinfo – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab8096b79cfbb91e4b65256c84ab1ba01207d9ed
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146991"
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