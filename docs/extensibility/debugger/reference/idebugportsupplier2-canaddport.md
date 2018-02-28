---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6b493229ab33f628c54580711604b16a4e2b5c5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
Ověřuje, že port dodavatele můžete přidat nové porty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud port je možné přidat, vrátí `S_OK`, jinak vrátí `S_FALSE` udávajících žádné porty lze přidat do tohoto portu dodavatele.  
  
## <a name="remarks"></a>Poznámky  
 Volání před voláním této metody [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) metoda vzhledem k tomu, že druhá metoda vytvoří port, jakož i přidávání, což může být časově náročná operace.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)