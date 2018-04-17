---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 612a065286723e3c2b68a9ce5bd31c850d030959
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
Načte sekvenci bajtů, počínaje daného umístění.  
  
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
 [v] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde má být zahájen čtení bajtů.  
  
 `dwCount`  
 [v] Počet bajtů ke čtení. Také určuje, jak `rgbMemory` pole.  
  
 `rgbMemory`  
 [ve out] Pole zadá počet bajtů ve skutečnosti přečíst.  
  
 `pdwRead`  
 [out] Vrátí počet bajtů souvislé ve skutečnosti číst.  
  
 `pdwUnreadable`  
 [ve out] Vrátí počet bajtů, nejde přečíst. Může mít hodnotu null, pokud je klient nemá o počet bajtů nečitelná.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud jsou požadovány 100 bajtů a první 50 čitelný, dalších 20 nečitelná a zbývajících 30 jsou čitelný, tato metoda vrátí hodnotu:  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 V takovém případě protože `*pdwRead + *pdwUnreadable < dwCount`, volající musí provést další volání číst zbývající 30 bajtů původní 100 požadovaný a [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt předaná `pStartContext` parametr musí být rozšířené podle 70.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)