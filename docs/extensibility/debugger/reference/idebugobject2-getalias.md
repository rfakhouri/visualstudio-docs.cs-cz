---
title: IDebugObject2::GetAlias | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetAlias
helpviewer_keywords:
- IDebugObject2::GetAlias method
ms.assetid: aa6824d5-c932-42ba-8713-950e7d1fb42f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: db9156e01843e859a2279e43f73c00bee21b3e9c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308741"
---
# <a name="idebugobject2getalias"></a>IDebugObject2::GetAlias
Získá alias přidružené k tomuto objektu, pokud existuje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetAlias(
   IDebugAlias** ppAlias
);
```

```csharp
int GetAlias(
   out IDebugAlias ppAlias
);
```

## <a name="parameters"></a>Parametry
`ppAlias`\
[out] Vrátí [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) objekt reprezentující alias pro tento objekt; v opačném případě vrátí hodnotu null.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Alias pro objekt je vytvořen voláním [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) metody.

## <a name="see-also"></a>Viz také:
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)