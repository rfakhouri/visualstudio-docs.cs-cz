---
title: IEnumDebugPortSuppliers2::Reset | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Next
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Next
ms.assetid: f69cbacf-da9d-4b22-b8a2-abd9b8c131f2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f34b73bbdd36dbf7d98885b48b0cd8fdf8dc4d7c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164679"
---
# <a name="ienumdebugportsuppliers2reset"></a>IEnumDebugPortSuppliers2::Reset
Obnoví výčtu na první prvek.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md) metoda vrátí první prvek výčtu.

## <a name="see-also"></a>Viz také
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)