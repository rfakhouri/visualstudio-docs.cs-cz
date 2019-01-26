---
title: EXCEPTION_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e255695cd461f5c272bc65f695d8935ab892d034
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960240"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
Popisuje výjimku nebo chyb za běhu vyvolané laděnému programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagEXCEPTION_INFO {   
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   BSTR            bstrExceptionName;  
   DWORD           dwCode;  
   EXCEPTION_STATE dwState;  
   GUID            guidType;  
} EXCEPTION_INFO;  
```  
  
```csharp  
public struct EXCEPTION_INFO {   
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public string         bstrExceptionName;  
   public uint           dwCode;  
   public uint           dwState;  
   public Guid           guidType;  
};  
```  
  
## <a name="members"></a>Členové  
 pProgram  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program, ve kterém k výjimce došlo.  
  
 bstrProgramName  
 Název programu, ve kterém k výjimce došlo.  
  
 bstrExceptionName  
 Název výjimky.  
  
 dwCode  
 Identifikační kód chyby výjimky nebo za běhu.  
  
 dwState  
 Hodnota z [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) výčet, který definuje stav výjimky.  
  
 guidType  
 Identifikátor GUID jazyka, buď `guidLang` nebo `guidEng`.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předán jako parametr [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) a [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) metody. Tato struktura je také předat [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) metoda být vyplněna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)