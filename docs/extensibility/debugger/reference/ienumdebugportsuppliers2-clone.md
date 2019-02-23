---
title: IEnumDebugPortSuppliers2::Clone | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Clone
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Clone
ms.assetid: 98b9914d-4f32-44da-b422-68830bce44b4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9ead6e4d2aa236c516a4180d8c08d62f91a34d62
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716711"
---
# <a name="ienumdebugportsuppliers2clone"></a>IEnumDebugPortSuppliers2::Clone
Vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone(
   IEnumDebugPortSuppliers2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugPortSuppliers2 ppEnum
);
```

#### <a name="parameters"></a>Parametry
 `ppEnum`

 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.

## <a name="see-also"></a>Viz také
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)