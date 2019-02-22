---
title: IDebugEngine2::RemoveAllSetExceptions | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveAllSetExceptions
helpviewer_keywords:
- IDebugEngine2::RemoveAllSetExceptions
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8f5eb2542fa16d86dd342ae0e2783ac03ca69ee4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703406"
---
# <a name="idebugengine2removeallsetexceptions"></a>IDebugEngine2::RemoveAllSetExceptions
Odebere seznam výjimek, integrovaném vývojovém prostředí má nastavit pro konkrétní architekturu za běhu nebo jazyk.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT RemoveAllSetExceptions( 
   REFGUID guidType
);
```

```csharp
int RemoveAllSetExceptions( 
   ref Guid guidType
);
```

#### <a name="parameters"></a>Parametry
 `guidType`

 [in] Identifikátor GUID pro jazyk nebo identifikátor GUID pro ladicí stroj, který je specifický pro architekturu za běhu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Výjimky odebrat touto metodou byly nastavené zásadami předchozích volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) metody.

 Chcete-li odebrat určité výjimky, zavolejte [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)