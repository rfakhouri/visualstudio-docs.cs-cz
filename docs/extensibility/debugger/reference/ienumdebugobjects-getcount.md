---
title: IEnumDebugObjects::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::GetCount
helpviewer_keywords:
- IEnumDebugObjects::GetCount method
ms.assetid: 9cbc5db4-03ae-479f-a664-13cad66ad210
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9ec21965c90680837c021a6bac8cafabd2a7ecb0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679618"
---
# <a name="ienumdebugobjectsgetcount"></a>IEnumDebugObjects::GetCount
Tato metoda vrátí počet prvků ve výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetCount(
   [out] ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

#### <a name="parameters"></a>Parametry
 `pcelt`

 [out] Vrátí počet prvků ve výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, která určuje, že je potřeba je implementovat pouze další, klonování, přeskočit a obnovení.

## <a name="see-also"></a>Viz také
- [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)