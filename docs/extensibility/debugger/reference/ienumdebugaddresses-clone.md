---
title: IEnumDebugAddresses::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugAddresses::Clone
helpviewer_keywords:
- IEnumDebugAddresses::Clone method
ms.assetid: 71189a00-34eb-4c71-b96e-8bd6e70c6966
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 061f893d83f6fc2225ccc3219f1243338b55a404
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681826"
---
# <a name="ienumdebugaddressesclone"></a>IEnumDebugAddresses::Clone
Tato metoda vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone(
   IEnumDebugAddresses** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugAddresses ppEnum
);
```

#### <a name="parameters"></a>Parametry
 `ppEnum`

 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.

## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.

## <a name="see-also"></a>Viz také
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)