---
title: IDebugMemoryContext2::GetInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugMemoryContext2::GetInfo method
ms.assetid: 08c7f091-1816-4d64-8834-f9ecaac5c58d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a42c16b260d9d4a0170cf20f9cab3b23682cf825
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718570"
---
# <a name="idebugmemorycontext2getinfo"></a>IDebugMemoryContext2::GetInfo
Načte [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktura, která popisuje kontextu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetInfo( 
   CONTEXT_INFO_FIELDS dwFields,
   CONTEXT_INFO*       pInfo
);
```

```csharp
int GetInfo(
   enum_CONTEXT_INFO_FIELDS dwFields,
   CONTEXT_INFO[]           pinfo
);
```

#### <a name="parameters"></a>Parametry
 `dwFields`

 [in] Kombinace příznaků z [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) výčet důvody, které pole [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktury mají být vyplnit.

 `pInfo`

 [out v] `CONTEXT_INFO` Struktura, která je vyplněna.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)
- [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)