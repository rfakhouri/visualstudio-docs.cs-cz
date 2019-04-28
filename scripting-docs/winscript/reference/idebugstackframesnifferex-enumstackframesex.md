---
title: IDebugStackFrameSnifferEx::EnumStackFramesEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrameSnifferEx.EnumStackFramesEx
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrameSnifferEx::EnumStackFramesEx
ms.assetid: b656b581-aff0-4984-8d8a-a1c7a8e6558a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8969c279e4eb2c2966e297317a25a60f12be68a9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63005716"
---
# <a name="idebugstackframesnifferexenumstackframesex"></a>IDebugStackFrameSnifferEx::EnumStackFramesEx
Vrátí enumerátor rámce zásobníku pro aktuální vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumStackFramesEx(  
   DWORD_PTR                dwSpMin,  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwSpMin`  
 [in] Dolní mez adresu pro výčet rámců zásobníku.  
  
 `ppedsf`  
 [out] Enumerátor rámce zásobníku pro aktuální vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Enumerátor rámce zásobníku vrátí počet snímků, spouští se v horní části zásobníku s nedávno vložené rámce. Enumerátor obsahuje pouze rámce zásobníku pomocí adresy větší než nebo rovna hodnotě `dwSpMin`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrameSnifferEx – rozhraní](../../winscript/reference/idebugstackframesnifferex-interface.md)