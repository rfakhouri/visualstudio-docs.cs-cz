---
title: IDebugPortSupplier2::AddPort | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::AddPort
helpviewer_keywords:
- IDebugPortSupplier2::AddPort
ms.assetid: df491161-6bf3-4fcc-b478-b9ec88ec995f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 05222901081fe3ba93f4648f3a2689d3d9a5c6ea
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204481"
---
# <a name="idebugportsupplier2addport"></a>IDebugPortSupplier2::AddPort
Přidá port.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT AddPort( 
   IDebugPortRequest2* pRequest,
   IDebugPort2**       ppPort
);
```

```csharp
int AddPort( 
   IDebugPortRequest2 pRequest,
   out IDebugPort2    ppPort
);
```

## <a name="parameters"></a>Parametry
`pRequest`\
[in] [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) objekt, který popisuje port, který chcete přidat.

`ppPort`\
[out] Vrátí [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objekt, který reprezentuje port.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda ve skutečnosti vytváří požadovaný port, jakož i přidáním do dodavatele portu vnitřní seznam aktivních portů. [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) metodu lze volat nejprve aby se vyhnuli prodlevám možné časově náročné.

## <a name="see-also"></a>Viz také:
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)