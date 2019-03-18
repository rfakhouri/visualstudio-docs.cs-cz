---
title: Ijsdebugdatatarget::FreeVirtualMemory – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.FreeVirtualMemory
apilocation:
- jscript9diag.dll
ms.assetid: ea54bad3-9ae3-436b-974d-70fc7fffefd6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf450c03d996a47f9dcd00899ddee46b75d6df32
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146302"
---
# <a name="ijsdebugdatatargetfreevirtualmemory-method"></a>IJsDebugDataTarget::FreeVirtualMemory – metoda
Uvolní a/nebo rozváže oblast paměti v rámci virtuálního adresového prostoru cílového procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT FreeVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD freeType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] Adresa v cílovém procesu, kde by měla být paměť uvolněna.  
  
 `size`  
 [in] Počet bajtů, které mají být uvolněny. Pokud chcete uvolnit oblast paměti, tato hodnota musí být nula.  
  
 `freeType`  
 [in] Označuje typ volné operace k provedení. Obvykle se jedná o MEM_RELEASE (0x8000), který uvolní zadanou oblast stránek. Po provedení této operace jsou stránky ve volném stavu. MEM_DECOMMIT (0x4000) lze použít místo toho pro zrušení stránky bez.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Další informace najdete v tématu ve VirtualFree Win32 API.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)