---
title: IDebugMemoryContext2::Compare | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9994f99759d570780729fe1c62e6604786e4eb90
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347032"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Porovná paměti kontext, který má každý kontext v daném poli způsobem indikován porovnání příznaky, které vrací index první kontextu, který se shoduje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Compare( 
   CONTEXT_COMPARE        compare,
   IDebugMemoryContext2** rgpMemoryContextSet,
   DWORD                  dwMemoryContextSetLen,
   DWORD*                 pdwMemoryContext
);
```

```csharp
int Compare(
   enum_CONTEXT_COMPARE   compare,
   IDebugMemoryContext2[] rgpMemoryContextSet,
   uint                   dwMemoryContextSetLen,
   out uint               pdwMemoryContext
);
```

## <a name="parameters"></a>Parametry
`compare`\
[in] Hodnota z [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) výčet, který určuje typ porovnání.

`rgpMemoryContextSet`\
[in] Odkazy na pole [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekty pro porovnání.

`dwMemoryContextSetLen`\
[in] Počet kontextů v `rgpMemoryContextSet` pole.

`pdwMemoryContext`\
[out] Vrátí index prvního paměti kontextu, který vyhovuje porovnání.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_COMPARE_CANNOT_COMPARE` Pokud nelze porovnat dva kontexty.

## <a name="remarks"></a>Poznámky
 Ladicí stroj (DE) nemá pro podporu všech typů porovnávání, ale musí podporovat alespoň `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` a `CONTEXT_SAME_SCOPE`.

## <a name="see-also"></a>Viz také:
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)