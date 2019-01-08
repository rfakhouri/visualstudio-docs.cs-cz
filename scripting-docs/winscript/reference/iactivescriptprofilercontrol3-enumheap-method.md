---
title: Iactivescriptprofilercontrol3::enumheap – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2799d06d-20dd-4c12-9646-554c0ea3606e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25e81a4aa631c142d4444c0578742f68001a108d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097016"
---
# <a name="iactivescriptprofilercontrol3enumheap-method"></a>IActiveScriptProfilerControl3::EnumHeap – metoda
Vrátí rozhraní ([iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)), který lze použít k iteraci objektů haldy GC v rámci přidruženého skriptovacího modulu.  
  
 Můžete volat tuto metodu v ladění nebo uvolnění režimu. Tuto metodu lze volat, když je vlákno UI nečinné. Po zavolání metody by měla být prováděny žádné operace proti skriptovacímu modulu s výjimkou [iactivescriptprofilerheapenum::Next – metoda](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) dokud [iactivescriptprofilerheapenum::Next – metoda](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)nevrátí hodnotu S_FALSE nebo [iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) se uvolní ukazatel rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumHeap([out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppEnum  
 [out] Vrátí [iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT.