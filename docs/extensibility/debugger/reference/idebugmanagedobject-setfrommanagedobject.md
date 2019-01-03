---
title: IDebugManagedObject::SetFromManagedObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 92b1e794dea8d64a8c41dfd4a85627c642d438f0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53901776"
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
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)