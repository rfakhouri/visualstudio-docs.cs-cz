---
title: IDebugManagedObject::SetFromManagedObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5fa81c34f18d6f1d3980da8d53c65f5ef58c05f3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180601"
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
Nastaví hodnotu vlastnosti instance objekt třídy hodnoty z instance třídy hodnotu zadat jako parametr.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetFromManagedObject( 
   IUnknown* pManagedObject
);
```

```csharp
int SetFromManagedObject(
   object pManagedObject
);
```

#### <a name="parameters"></a>Parametry
 `pManagedObject`

 [in] Rozhraní, která představuje spravovaný objekt, který obsahuje novou hodnotu.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda se používá ke změně spravovaný objekt reprezentovaný hodnotou [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) objektu.

## <a name="see-also"></a>Viz také
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)