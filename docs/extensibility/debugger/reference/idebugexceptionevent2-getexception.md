---
title: IDebugExceptionEvent2::GetException | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExceptionEvent2::GetException
helpviewer_keywords:
- IDebugExceptionEvent2::GetException
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 79385348aa9290f26a34b99dbd2d6f68cb92dc8a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680279"
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
- [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)