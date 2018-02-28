---
title: IDebugThread2::Resume | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5de844c3b07a509f266e2f9d278d1f78bea2b089
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
Pokračuje v provádění vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwSuspendCount`  
 [out] Vrátí počet pozastavit po operaci obnovení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každé volání na tato metoda snižuje počet pozastavit dokud nedosáhne 0 na dobu, je ve skutečnosti obnoveno provádění. Tento počet pozastavit se zobrazí v **vláken** okno ladění.  
  
 Pro každé volání tuto metodu, musí být předchozího volání [pozastavit](../../../extensibility/debugger/reference/idebugthread2-suspend.md) metoda. Počet pozastavit Určuje, jak často `IDebugThread2::Suspend` , pokud byla volána metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Pozastavit](../../../extensibility/debugger/reference/idebugthread2-suspend.md)