---
title: IDebugObject::GetMemoryContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetMemoryContext
helpviewer_keywords:
- IDebugObject::GetMemoryContext method
ms.assetid: 6760a0d3-a898-4e81-b68f-c45c584b225b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 38f913952c3e2f58b0d7bd2a27ac20e8f754da2f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323628"
---
# <a name="idebugobjectgetmemorycontext"></a>IDebugObject::GetMemoryContext
Získá kontext paměti, který představuje adresu hodnotu objektu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMemoryContext( 
   IDebugMemoryContext2** pContext
);
```

```csharp
int GetMemoryContext(
   ref IDebugMemoryContext2 pContext
);
```

## <a name="parameters"></a>Parametry
`pContext`\
[out] Vrátí [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt představující adresu hodnotu objektu.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kontext vrácené paměti určuje adresu hodnotu reprezentovaný tímto objektem [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu.

## <a name="see-also"></a>Viz také:
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)