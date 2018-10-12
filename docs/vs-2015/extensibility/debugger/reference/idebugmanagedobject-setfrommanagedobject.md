---
title: IDebugManagedObject::SetFromManagedObject | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f1e4b0aa60cdf20a154305238de74ccdd72cd26
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49280745"
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví hodnotu vlastnosti instance objekt třídy hodnoty z instance třídy hodnotu zadat jako parametr.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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

