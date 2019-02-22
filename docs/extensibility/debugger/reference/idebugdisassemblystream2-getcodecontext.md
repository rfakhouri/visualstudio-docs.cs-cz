---
title: IDebugDisassemblyStream2::GetCodeContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetCodeContext
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeContext
ms.assetid: a6d0ae82-7617-4915-9713-369abe3e2e53
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 268d1f4f80c032932663e7adf9ba9f2063fa90a8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706363"
---
# <a name="idebugdisassemblystream2getcodecontext"></a>IDebugDisassemblyStream2::GetCodeContext
Vrátí objekt kontextu kód odpovídající identifikátor umístění zadaného kódu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetCodeContext( 
   UINT64               uCodeLocationId,
   IDebugCodeContext2** ppCodeContext
);
```

```csharp
int GetCodeContext( 
   ulong                  uCodeLocationId,
   out IDebugCodeContext2 ppCodeContext
);
```

#### <a name="parameters"></a>Parametry
 `uCodeLocationId`

 [in] Určuje identifikátor umístění kódu. V části poznámky [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metoda popis identifikátor umístění kódu.

 `ppCodeContext`

 [out] Vrátí [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který reprezentuje kontext přidružený kód.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Identifikátor umístění kódu může být vrácen z volání [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md) metody a může objevit v [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury.

 Chcete-li převést kontext kódu identifikátor umístění kódu, zavolejte [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)
- [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)