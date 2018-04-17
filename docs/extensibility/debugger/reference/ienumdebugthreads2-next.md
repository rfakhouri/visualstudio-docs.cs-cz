---
title: IEnumDebugThreads2::Next | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugThreads2::Next
helpviewer_keywords:
- IEnumDebugThreads2::Next
ms.assetid: bcffd954-3c67-4867-96f3-041ddb3e34d4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 357dfb9a2fcc2385de21e6483ce30853190521dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugthreads2next"></a>IEnumDebugThreads2::Next
Vrací další sadu elementů z výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Next(  
   ULONG           celt,  
   IDebugThread2** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint            celt,  
   IDebugThread2[] rgelt,  
   ref uint        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet elementů k načtení. Také určuje maximální velikost `rgelt` pole.  
  
 `rgelt`  
 [ve out] Pole [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) elementy k vyplnění.  
  
 `pceltFetched`  
 [out] Vrátí počet elementů ve skutečnosti, vrátí se v `rgelt`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud méně než požadovaný počet elementů nemohl být vrácen; jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)