---
title: IDebugExceptionEvent2::GetException | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExceptionEvent2::GetException
helpviewer_keywords:
- IDebugExceptionEvent2::GetException
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8fad5aca8dcb548718c6acabb5c58e8c31592558
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53950800"
---
# <a name="idebugexceptionevent2getexception"></a>IDebugExceptionEvent2::GetException
Získá podrobný popis výjimky, která vyvolala Tato událost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetException(   
   EXCEPTION_INFO* pExceptionInfo  
);  
```  
  
```csharp  
int GetException(   
   EXCEPTION_INFO[] pExceptionInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pExceptionInfo`  
 [out v] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktura, která se vyplní popis výjimky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [Jenom C++] Volající zodpovídá za všechny řetězce v uvolnění [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktury a uvolnění [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objektu ve struktuře.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)