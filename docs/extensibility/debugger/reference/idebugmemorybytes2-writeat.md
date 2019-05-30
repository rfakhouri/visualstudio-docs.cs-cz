---
title: IDebugMemoryBytes2::WriteAt | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5eefaee08d64952681e91711cdf8347186123e57
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347139"
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
Zapíše zadaný počet bajtů paměti, spouští se na zadané adrese.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WriteAt( 
   IDebugMemoryContext2* pStartContext,
   DWORD                 dwCount,
   BYTE*                 rgbMemory
);
```

```csharp
int WriteAt(
   IDebugMemoryContext2 pStartContext,
   uint                 dwCount,
   byte[]               rgbMemory
);
```

## <a name="parameters"></a>Parametry
`pStartContext`\
[in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde začít psát bajtů.

`dwCount`\
[in] Počet bajtů k zápisu.

`rgbMemory`\
[in] Bajty k zápisu. Toto pole je považován za nejméně `dwCount` bajty.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud ne všechny bajty může být napsaná nebo vrátí kód chyby (obvykle `E_FAIL`).

## <a name="remarks"></a>Poznámky
 Pokud počáteční adresa není v rámci okna paměť představovaného tímto rozhraním [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) objektů, dojde k žádné psaní a chybovým kódem `E_FAIL` je vrácena – i v případě, že do paměťový prostor se překrývá velikost pro zápis.

## <a name="see-also"></a>Viz také:
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)