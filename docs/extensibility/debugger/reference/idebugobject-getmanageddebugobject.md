---
title: IDebugObject::GetManagedDebugObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b6738c70b75ff1e2f393b59e330ce57f2232de61
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62918525"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
Vytvoří kopii spravovaný objekt v adresním prostoru ladicího stroje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetManagedDebugObject( 
   IDebugManagedObject** ppObject
);
```

```csharp
int GetManagedDebugObject(
   out IDebugManagedObject ppObject
);
```

#### <a name="parameters"></a>Parametry
 `ppObject`

 [out] Vrátí [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) představující nově vytvořený objekt spravovaný objekt.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby. Vrátí E_FAIL tato [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nepředstavuje instanci třídy spravované hodnotě.

## <a name="remarks"></a>Poznámky
 To [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu musí představovat instanci třídy spravované hodnotu, například `System.Decimal` instance. Tím, že místní kopie režií volací [vyhodnotit](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) se odstraní.

## <a name="see-also"></a>Viz také
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)