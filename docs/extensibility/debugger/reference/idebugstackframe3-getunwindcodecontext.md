---
title: IDebugStackFrame3::GetUnwindCodeContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame3::GetUnwindCodeContext
helpviewer_keywords:
- IDebugStackFrame3::GetUnwindCodeContext method
ms.assetid: b25f7e7d-2b24-48e4-93b3-829e61d73ebf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 032e7f05ebb1ba8367ffaa7ef1ffbfb974aa0df1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54933565"
---
# <a name="idebugstackframe3getunwindcodecontext"></a>IDebugStackFrame3::GetUnwindCodeContext
Vrátí kontext kódu představující umístění, pokud operace unwind zásobníku došlo k chybě.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetUnwindCodeContext(  
   IDebugCodeContext2 **ppCodeContext  
);  
```  
  
```csharp  
int GetUnwindCodeContext(  
   out IDebugCodeContext2 ppCodeContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppCodeContext`  
 [out] Vrátí [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který představuje místní umístění kódu, pokud došlo k odvíjení zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 I když tato metoda může vrátit kontext kódu pro umístění po odvíjení zásobníku, neznamená nutně, že odvíjení zásobníku ve skutečnosti může dojít v aktuální rámec zásobníku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)