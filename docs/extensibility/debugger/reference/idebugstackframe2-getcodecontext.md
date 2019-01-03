---
title: IDebugStackFrame2::GetCodeContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame2::GetCodeContext
helpviewer_keywords:
- IDebugStackFrame2::GetCodeContext
ms.assetid: 93d66159-a41d-49ef-982f-91bb4d073b74
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a3a4446c1f466767ca91a6e9da22af7790c20b7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986554"
---
# <a name="idebugstackframe2getcodecontext"></a>IDebugStackFrame2::GetCodeContext
Získá kontext kódu pro tento rámec zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCodeContext (   
   IDebugCodeContext2** ppCodeCxt  
);  
```  
  
```csharp  
int GetCodeContext (   
   out IDebugCodeContext2 ppCodeCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppCodeCxt`  
 [out] Vrátí [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který představuje aktuální ukazatel příkazu v tomto bloku zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)