---
title: IDebugManagedObject::GetManagedObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
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
ms.openlocfilehash: 2be150d3ce1103f8f47438af7ac8fcfcba8519da
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922909"
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
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)