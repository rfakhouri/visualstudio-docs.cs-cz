---
title: IDebugStackFrame2::GetPhysicalStackRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ac507c2eac00d025a36bed3e4c3461a6b3fab2f0
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212867"
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
Získá vyjádření závislé na počítači rozsahu fyzické adresy přidružený blok zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPhysicalStackRange ( 
   UINT64* paddrMin,
   UINT64* paddrMax
);
```

```csharp
int GetPhysicalStackRange ( 
   out ulong paddrMin,
   out ulong paddrMax
);
```

## <a name="parameters"></a>Parametry
`paddrMin`\
[out] Vrátí nejnižší fyzické adresy přidružené k tento rámec zásobníku.

`paddrMax`\
[out] Vrátí nejvyšší fyzické adresy přidružené k tento rámec zásobníku.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Informace o vrácený touto metodou používá správce ladění relace (SDM) řazení zásobníku.

 Předpokládá se, že zásobník volání roste dolů, to znamená, že jsou přidány nové bloky zásobníku stále nižší adresy paměti. Za běhu architektury musíte zadat rozsahy adres fyzického zásobníku, které odpovídají tento předpoklad.

## <a name="see-also"></a>Viz také:
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)