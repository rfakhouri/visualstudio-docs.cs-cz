---
title: IDebugStackFrame2::GetPhysicalStackRange | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2cf0db9fa776116f1536ae137444160385a8b6a1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347716"
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