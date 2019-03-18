---
title: IActiveScriptProfilerHeapEnum::GetNameIdMap | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88514c93-850b-48d4-9a68-1e27d7411f0d
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3284557bf71a038d884c1f8786755b7761770e21
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157383"
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