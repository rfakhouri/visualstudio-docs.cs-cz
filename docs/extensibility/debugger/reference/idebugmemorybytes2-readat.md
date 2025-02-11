---
title: IDebugMemoryBytes2::ReadAt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a1083239dbb00e5b953fe7a72c27a350ffe34cc2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314304"
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
Načte posloupnost bajtů, spouští se v daném umístění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ReadAt( 
   IDebugMemoryContext2* pStartContext,
   DWORD                 dwCount,
   BYTE*                 rgbMemory,
   DWORD*                pdwRead,
   DWORD*                pdwUnreadable
);
```

```csharp
int ReadAt(
   IDebugMemoryContext2 pStartContext,
   uint                 dwCount,
   byte[]               rgbMemory,
   out uint             pdwRead,
   ref uint             pdwUnreadable
);
```

## <a name="parameters"></a>Parametry
`pStartContext`\
[in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde začne číst bajty.

`dwCount`\
[in] Počet bajtů ke čtení. Také určuje délku `rgbMemory` pole.

`rgbMemory`\
[out v] Pole se vyplní počet bajtů ve skutečnosti číst.

`pdwRead`\
[out] Vrátí počet souvislých skutečně přečtených bajtů.

`pdwUnreadable`\
[out v] Vrátí počet bajtů, nejde přečíst. Může mít hodnotu null, pokud je klient nemá o počtu bajtů nejde přečíst.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud požadavku na 100 bajtů a prvních 50 jsou čitelné, dalších 20 jsou nejde přečíst a zbývajících 30 jsou čitelné, vrátí tato metoda:

 *`pdwRead` = 50

 *`pdwUnreadable` = 20

 V takovém případě protože `*pdwRead + *pdwUnreadable < dwCount`, volající musí provést další volání číst zbývající bajty 30 původní 100 požadované a [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) předaný objekt `pStartContext` parametr musí být rozšířené podle 70.

## <a name="see-also"></a>Viz také:
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)