---
title: IDebugObject::IsEqual | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 527d0bf7dcc7841516c3ae620130aa346841d0a1
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66202870"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
Porovná objekt s tímto objektem.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsEqual( 
   IDebugObject* pObject,
   BOOL*         pfIsEqual
);
```

```csharp
int IsEqual(
   IDebugObject pObject,
   out int      pfIsEqual
);
```

## <a name="parameters"></a>Parametry
`pObject`\
[in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt představující objekt k porovnání s.

`pfIsEqual`\
[out] Vrátí nenulovou (`TRUE`) Pokud jsou hodnoty objekty stejné; jinak, vrátí hodnotu 0 (`FALSE`).

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Obvykle tuto metodu můžete porovnat adresy hodnoty reprezentované `pObject` parametr a to [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt; Pokud adresy jsou si rovny, pak objekty lze považovat za stejné.

## <a name="see-also"></a>Viz také:
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)