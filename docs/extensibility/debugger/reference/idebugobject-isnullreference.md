---
title: IDebugObject::IsNullReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::IsNullReference
helpviewer_keywords:
- IDebugObject::IsNullReference method
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1fb6b5c0692ec43feec0cf4de48d9ce730b0032e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323519"
---
# <a name="idebugobjectisnullreference"></a>IDebugObject::IsNullReference
Ověřuje, zda tento objekt je odkaz s hodnotou null.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsNullReference( 
   BOOL* pfIsNull
);
```

```csharp
int IsNullReference(
   out int pfIsNull
);
```

## <a name="parameters"></a>Parametry
`pfIsNull`\
[out] Vrátí nenulovou (`TRUE`) Pokud tento objekt je odkaz s hodnotou null; v opačném případě vrátí hodnotu 0 (`FALSE`).

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Odkaz s hodnotou null znamená, že prázdný objekt nebo objekt, který nebyl přiřazen.

## <a name="see-also"></a>Viz také:
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)