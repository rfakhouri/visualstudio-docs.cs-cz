---
title: IDebugDefaultPort2::GetPortNotify | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9c59687e86d236bc22d563c94e2caaedae5decf
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205130"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
Tato metoda načte [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) rozhraní pro tento port.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPortNotify(
   IDebugPortNotify2** ppPortNotify
);
```

```csharp
int GetPortNotify(
   out IDebugPortNotify2 ppPortNotify
);
```

## <a name="parameters"></a>Parametry
`ppPortNotify`\
[out] [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Za normálních okolností `QueryInterface` metoda je volána při implementaci objektu [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní získat [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) rozhraní. Nicméně existují okolnosti, ve kterých požadované rozhraní je implementováno na jiný objekt. Tato metoda skrývá situace a vrátí `IDebugPortNotify2` rozhraní z objektu nejvhodnější.

## <a name="see-also"></a>Viz také:
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)