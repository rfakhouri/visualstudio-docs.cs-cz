---
title: IActiveScriptProfilerHeapEnum::GetNameIdMap | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88514c93-850b-48d4-9a68-1e27d7411f0d
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cdff1983524b9234d536a23378d300a0b815522d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092635"
---
# <a name="iactivescriptprofilerheapenumgetnameidmap"></a>IActiveScriptProfilerHeapEnum::GetNameIdMap
Vrátí řetězcové názvy odpovídají [profiler_heap_object_name_id – typ](../../winscript/reference/profiler-heap-object-name-id-type.md) hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetNameIdMap (    [out, size_is(,*pcelt)] LPCWSTR* pNameList[],     [out] UINT *pcelt);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pNameList`  
 [out] Pole názvy přidružené [profiler_heap_object_name_id – typ](../../winscript/reference/profiler-heap-object-name-id-type.md) hodnoty.  
  
 `pcelt`  
 [out] Počet názvů v poli.  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT.