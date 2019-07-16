---
title: IDebugPortSupplier2::CanAddPort | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e4ec078650446d3511ed9c5bdc8ee3ec0191487d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68188346"
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
