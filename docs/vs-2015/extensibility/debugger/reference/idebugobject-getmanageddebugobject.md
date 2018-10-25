---
title: IDebugObject::GetManagedDebugObject | Dokumentace Microsoftu
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
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 07ec736f44529284fbe68e296b1bf6600ef7229e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49940564"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří kopii spravovaný objekt v adresním prostoru ladicího stroje.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

