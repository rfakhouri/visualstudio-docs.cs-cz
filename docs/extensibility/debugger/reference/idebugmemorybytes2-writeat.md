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
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ad3e4c14c28f220a28e8d9aa65ddb1b6e6a3af0a
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210555"
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