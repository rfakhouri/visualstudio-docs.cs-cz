---
title: IDebugThread2::GetThreadId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugThread2::GetThreadId
helpviewer_keywords:
- IDebugThread2::GetThreadId
ms.assetid: db8b1c07-6b86-47f9-b292-bac19c276d36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 74b7e0a2e2754361899a65e66ecac8a75be55722
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949438"
---
# <a name="idebugthread2getthreadid"></a>IDebugThread2::GetThreadId
Získá identifikátor systému.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetThreadId (   
   DWORD* pdwThreadId  
);  
```  
  
```csharp  
int GetThreadId (   
   out uint pdwThreadId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwThreadId`  
 [out] Vrátí identifikátor systému.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 ID vlákna slouží k identifikaci vlákno mezi ostatní vlákna v procesu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CProgram` objekt, který implementuje [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) rozhraní.  
  
```cpp  
HRESULT CProgram::GetThreadId(DWORD* pdwThreadId) {     
   *pdwThreadId = GetCurrentThreadId();    
   return NOERROR;    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)