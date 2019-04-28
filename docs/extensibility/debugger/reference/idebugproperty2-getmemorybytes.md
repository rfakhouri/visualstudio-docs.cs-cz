---
title: IDebugProperty2::GetMemoryBytes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetMemoryBytes
helpviewer_keywords:
- IDebugProperty2::GetMemoryBytes
ms.assetid: b32042ed-7a06-4b4a-99ef-fe03b0aa61cc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 12d35ace2d5a2b2f0c10d4b2e0a44a05f52942fd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916655"
---
# <a name="idebugproperty2getmemorybytes"></a>IDebugProperty2::GetMemoryBytes
Získá počet bajtů paměti, které tvoří hodnotu vlastnosti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetMemoryBytes ( 
   IDebugMemoryBytes2** ppMemoryBytes
);
```

```csharp
int GetMemoryBytes ( 
   out IDebugMemoryBytes2 ppMemoryBytes
);
```

#### <a name="parameters"></a>Parametry
 `ppMemoryBytes`

 [out] Vrátí [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) objekt, který můžete použít k načtení paměť, která obsahuje hodnotu vlastnosti.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETMEMORYBYTES_NO_MEMORY_BYTES` Pokud nejsou žádné bajty paměti k načtení.

## <a name="see-also"></a>Viz také
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)