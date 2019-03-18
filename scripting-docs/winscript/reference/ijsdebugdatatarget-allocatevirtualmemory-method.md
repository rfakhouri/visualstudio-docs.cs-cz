---
title: Ijsdebugdatatarget::allocatevirtualmemory – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.AllocateVirtualMemory
apilocation:
- jscript9diag.dll
ms.assetid: 1d3a77b0-c1de-4a0c-a759-3e0c68fd96dd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c04bf21882ec39054c74f060eaa2c6f65ac0b4d6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58148461"
---
# <a name="ijsdebugdatatargetallocatevirtualmemory-method"></a>IJsDebugDataTarget::AllocateVirtualMemory – metoda
Rezervuje a/nebo potvrdí změny v oblasti paměti v rámci virtuálního adresového prostoru cílového procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AllocateVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD allocationType,  
   DWORD pageProtection,  
   UINT64 *pAllocatedAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] Adresa v cílovém procesu, ve kterém potvrzena nebo vyhrazena paměť. Tato hodnota je obvykle nula, ve kterém případě systém zvolí adresu.  
  
 `size`  
 [in] Velikost oblasti paměti k přidělení v bajtech. Systém automaticky zaokrouhlí na hranici další stránky.  
  
 `allocationType`  
 [in] Označuje typ přidělení k provedení. To je obvykle MEM_COMMIT &#124; MEM_RESERVE (0x3000), který rezervuje a přidělení v jednom kroku.  
  
 `pageProtection`  
 [in] Ochrana paměti pro oblasti stránek, které mají být přiděleny. Pokud jsou přiděleny stránky, můžete zadat některou z konstant ochrany paměti (například PAGE_READWRITE, PAGE_EXECUTE).  
  
 `pAllocatedAddress`  
 [out] Základní adresa přidělené oblasti stránek.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Funkce inicializuje přidělenou paměť na nulu, pokud není použit MEM_RESET. Další informace najdete v tématu VirtualAlloc Win32 API.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)