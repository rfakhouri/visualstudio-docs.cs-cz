---
title: IDebugManagedObject::GetManagedObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject::GetManagedObject
helpviewer_keywords:
- IDebugManagedObject::GetManagedObject method
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6df3a4f69c62e7681eade705186c802a225f060
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62873384"
---
# <a name="idebugmanagedobjectgetmanagedobject"></a>IDebugManagedObject::GetManagedObject
Vrátí rozhraní, která představuje spravovaný objekt.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetManagedObject( 
   IUnknown** ppManagedObject
);
```

```cpp
int GetManagedObject(
   out object ppManagedObject
);
```

#### <a name="parameters"></a>Parametry
 `ppManagedObject`

 [out] Vrátí rozhraní, která představuje spravovaný objekt.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vrácené z této metody rozhraní může být dotázán na libovolném rozhraní implementovány pomocí spravované třídy, což její metody, která se má volat.

## <a name="see-also"></a>Viz také
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)