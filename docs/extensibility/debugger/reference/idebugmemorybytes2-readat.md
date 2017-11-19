---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4de46d516efca856deef6fa9070e466de73e258f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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