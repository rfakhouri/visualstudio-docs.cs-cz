---
title: Iactivescriptprofilercontrol5::enumheap2 – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: a25859eb-ac28-4a97-bcb3-33788982a76b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c90c536dee76d67fdb93dd205e8f6eedff6dcc7
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150800"
---
# <a name="iactivescriptprofilercontrol5enumheap2-method"></a>IActiveScriptProfilerControl5::EnumHeap2 – metoda
Vrátí rozhraní ([iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)), který lze použít k iteraci objektů haldy GC v rámci přidruženého skriptovacího modulu.  
  
 Můžete volat tuto metodu v ladění nebo uvolnění režimu. Tuto metodu lze volat, když je vlákno UI nečinné. Po zavolání metody by měla být prováděny žádné operace proti skriptovacímu modulu s výjimkou [iactivescriptprofilerheapenum::Next – metoda](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) dokud [iactivescriptprofilerheapenum::Next – metoda](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)nevrátí hodnotu S_FALSE nebo [iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) se uvolní ukazatel rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumHeap2(    [in] PROFILER_HEAP_ENUM_FLAGS enumFlags,    [out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>Parametry  
 enumFlags  
 Hodnota, která určuje, zda je přístupný Další informace o objektu, na který je odkazováno v objektovém vztahu. Další informace může určovat, zda je objekt, na který je odkazováno, metoda getter nebo setter. Další informace najdete v tématu [profiler_heap_enum_flags – výčet](../../winscript/reference/profiler-heap-enum-flags-enumeration.md).  
  
 ppEnum  
 [out] Vrátí [iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Výčet haldy, byla úspěšně dokončena.|  
|`E_OUTOFMEMORY`|Není k dispozici dostatek paměti k provedení výčtu haldy.|  
|`E_FAIL`|Došlo k vnitřní chybě.|