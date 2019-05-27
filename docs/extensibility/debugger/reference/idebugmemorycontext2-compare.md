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
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f04000d3e2675f766ae343836320aa7433ade87d
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211998"
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