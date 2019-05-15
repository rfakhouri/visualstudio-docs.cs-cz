---
title: IDebugBinder::Bind | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e3db6a0f5977591b12cb3c77bd1791905f82a087
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615172"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
Tato metoda načte místní paměti nebo objekt, který obsahuje aktuální hodnotu tohoto symbolu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Bind( 
   IDebugObject*  pContainer,
   IDebugField*   pField,
   IDebugObject** ppObject
);
```

```csharp
int Bind(
   IDebugObject     pContainer,
   IDebugField      pField,
   out IDebugObject ppObject
);
```

## <a name="parameters"></a>Parametry
`pContainer`\
[in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) , která obsahuje podřízené odkazuje `pField`.

`pField`\
[in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) představující symbol.

`ppObject`\
[out] Vrátí `IDebugObject` , která představuje výskyt symbolu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)