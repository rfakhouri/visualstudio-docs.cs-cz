---
title: IDebugBreakpointRequest3::GetRequestInfo2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3::GetRequestInfo2
helpviewer_keywords:
- IDebugBreakpointRequest3::GetRequestInfo2
ms.assetid: 33942e4a-0a0a-49e8-a693-004954f6d38a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 58c313ebc56035d40d4743b9411c476434c82123
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199760"
---
# <a name="idebugbreakpointrequest3getrequestinfo2"></a>IDebugBreakpointRequest3::GetRequestInfo2
Tato metoda získá informace zarážku požadavek, který popisuje tuto zarážku žádost.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetRequestInfo2(
   BPREQI_FIELDS      dwFields,
   BP_REQUEST_INFO2*  bBPRequestInfo
);
```

```csharp
int GetRequestInfo2(
   enum_BPREQI_FIELDS  dwFields,
   BP_REQUEST_INFO2[]  bBPRequestInfo
);
```

## <a name="parameters"></a>Parametry
`dwFields`\
[in] Kombinace příznaků z [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) výčet určující, které pole `pBPRequestInfo` mají být vyplněna.

`bBPRequestInfo`\
[out] [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktura být vyplněna.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Nejsou k dispozici další informace v této žádosti, než je vrácen z [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)
- [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
- [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)