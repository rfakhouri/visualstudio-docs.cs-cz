---
title: Ijsdebugdatatarget::readmemory – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadMemory
apilocation:
- jscript9diag.dll
ms.assetid: 664e0f7d-2007-45f4-b993-36fe8b1944e5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66d3709dadfc8da2feb7e6845a7aeaa357235d9e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089177"
---
# <a name="ijsdebugdatatargetreadmemory-method"></a>IJsDebugDataTarget::ReadMemory – metoda
Čtení paměti cílového procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ReadMemory(  
   UINT64 address,  
   JsDebugReadMemoryFlags flags,  
   BYTE *pBuffer,  
   DWORD size,  
   DWORD *pBytesRead  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] Základní adresa, ze které probíhá čtení paměti cílového procesu.  
  
 `flags`  
 [in] Příznaky určující chování ReadMemory.  
  
 `pBuffer`  
 [out] Vyrovnávací paměť, která obdrží obsah z adresního prostoru cílového procesu. Při selhání není obsah této vyrovnávací paměti.  
  
 `size`  
 [in] Počet bajtů ke čtení z procesu.  
  
 `pBytesRead`  
 [out] Určuje počet bajtů přečtených z cílového procesu. Pokud je jsdebugallowpartialread čisté, při úspěchu tato hodnota bude vždy přesně stejné jako vstupní velikost. Pokud je zadáno JsDebugAllowPartialRead, při úspěchu bude tato hodnota větší než nula.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Vrátí hodnotu S_OK při úspěchu a kódy selhání se používají pro všechny chyby. Vrátí E_JsDEBUG_INVALID_MEMORY_ADDRESS, pokud adresa není platná. Další informace naleznete v JsDebugAllowPartialRead.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)