---
title: IDebugPortSupplier2::CanAddPort | Dokumentace Microsoftu
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
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 534a95825b32f7159f191a99351cfe003376db0d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49894609"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Ověřuje, že dodavatele portu můžete přidat nové porty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud port, který lze přidat, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` k označení žádné porty lze přidat do tohoto dodavatele portu.  
  
## <a name="remarks"></a>Poznámky  
 Volání před voláním této metody [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) metody, protože tato metoda vytvoří port, jakož i přidáním, což může být časově náročná operace.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

