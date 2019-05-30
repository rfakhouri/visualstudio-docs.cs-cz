---
title: IDebugPortSupplier2::CanAddPort | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 37f4fd246c376d08ab3ca006c543b44c4db2d73d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340282"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
Ověřuje, že dodavatele portu můžete přidat nové porty.

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
 Pokud port, který lze přidat, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` k označení žádné porty lze přidat do tohoto dodavatele portu.

## <a name="remarks"></a>Poznámky
 Volání před voláním této metody [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) metody, protože tato metoda vytvoří port, jakož i přidáním, což může být časově náročná operace.

## <a name="see-also"></a>Viz také:
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)