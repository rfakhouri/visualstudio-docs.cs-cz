---
title: IDebugMemoryBytes2::ReadAt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 16c5df12b268fb53ebd5b6174cbf9225a868f048
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55023626"
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
Načte posloupnost bajtů, spouští se v daném umístění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde začne číst bajty.  
  
 `dwCount`  
 [in] Počet bajtů ke čtení. Také určuje délku `rgbMemory` pole.  
  
 `rgbMemory`  
 [out v] Pole se vyplní počet bajtů ve skutečnosti číst.  
  
 `pdwRead`  
 [out] Vrátí počet souvislých skutečně přečtených bajtů.  
  
 `pdwUnreadable`  
 [out v] Vrátí počet bajtů, nejde přečíst. Může mít hodnotu null, pokud je klient nemá o počtu bajtů nejde přečíst.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud požadavku na 100 bajtů a prvních 50 jsou čitelné, dalších 20 jsou nejde přečíst a zbývajících 30 jsou čitelné, vrátí tato metoda:  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 V takovém případě protože `*pdwRead + *pdwUnreadable < dwCount`, volající musí provést další volání číst zbývající bajty 30 původní 100 požadované a [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) předaný objekt `pStartContext` parametr musí být rozšířené podle 70.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)