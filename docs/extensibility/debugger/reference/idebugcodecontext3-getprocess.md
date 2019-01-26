---
title: IDebugCodeContext3::GetProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugCodeContext3::GetProcess
ms.assetid: e082e494-2255-4d9d-a5a9-6dadd904bea8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a7a340a48a6b997dd6fd812a850c4df33d667586
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948710"
---
# <a name="idebugcodecontext3getprocess"></a>IDebugCodeContext3::GetProcess
Získá referenci k rozhraní ladění procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProcess(   
   IDebugProcess2 **ppProcess  
);  
```  
  
```csharp  
public int GetProcess(   
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppProcess`  
 [out] Reference k rozhraní ladění procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugCodeContext** objekt, který zveřejňuje [IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md) rozhraní.  
  
```cpp  
HRESULT CDebugCodeContext::GetProcess(IDebugProcess2** ppProcess)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CDebugEngine> pEngine;  
    CComPtr<IDebugPort2> pPort2;  
  
    IfFalseGo( ppProcess, E_INVALIDARG );  
    *ppProcess = NULL;  
  
    IfFalseGo( m_pProgram, E_FAIL );  
    IfFailGo( ((CDebugProgram *)m_pProgram)->GetEngine(&pEngine) );  
    IfFailGo( pEngine->GetSDMProcess(ppProcess) );  
  
Error:  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)