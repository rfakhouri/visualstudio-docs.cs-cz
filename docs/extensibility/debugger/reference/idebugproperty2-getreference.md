---
title: IDebugProperty2::GetReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 49763b0f8a0d7d0c016326d69a22a57d8ff32403
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342935"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
Vrátí odkaz na hodnotu vlastnosti.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetReference(
   IDebugReference2** ppReference
);
```

```csharp
int GetReference(
   out IDebugReference2 ppReference
);
```

## <a name="parameters"></a>Parametry
`ppRererence`\
[out] Vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt představující odkaz na hodnotu vlastnosti.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby, obvykle `E_NOTIMPL` nebo `E_GETREFERENCE_NO_REFERENCE`.

## <a name="see-also"></a>Viz také:
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)