---
title: IDebugStackFrame2::GetInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetInfo
helpviewer_keywords:
- IDebugStackFrame2::GetInfo
ms.assetid: 19c6870b-b94e-453c-bf19-82ce95b79d26
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0aeb888b2cc81dac6157ef0944703227799e61e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868751"
---
# <a name="idebugstackframe2getinfo"></a>IDebugStackFrame2::GetInfo
Získá popis rámce zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetInfo ( 
   FRAMEINFO_FLAGS dwFieldSpec,
   UINT            nRadix,
   FRAMEINFO*      pFrameInfo
);
```

```csharp
int GetInfo ( 
   enum_FRAMEINFO_FLAGS dwFieldSpec,
   uint                 nRadix,
   FRAMEINFO[]          pFrameInfo
);
```

#### <a name="parameters"></a>Parametry
 `dwFieldSpec`

 [in] Kombinace příznaků z [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) výčet, který určuje, jaké pole `pFrameInfo` parametr mají být vyplněna.

 `nRadix`

 [in] Základ, který se má použít v jakékoli číselné informace o formátování.

 `pFrameInfo`

 [out] A [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktura, která se vyplní popis rámce zásobníku.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)
- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)