---
title: IDebugBinder::GetFunctionObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::GetFunctionObject
helpviewer_keywords:
- IDebugBinder::GetFunctionObject method
ms.assetid: 8fb789df-8f30-420d-8ca5-bb496a6738f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b69af018a1b5b1ddf743784f4736d7c2ac24d45f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712291"
---
# <a name="idebugbindergetfunctionobject"></a>IDebugBinder::GetFunctionObject
Tato metoda načte [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objekt použitý k vytvoření parametry funkce.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetFunctionObject( 
   IDebugFunctionObject **ppFunction
);
```

```csharp
int GetFunctionObject(
   out IDebugFunctionObject ppFunction
);
```

#### <a name="parameters"></a>Parametry
 `ppFunction`

 [out] Vrátí [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní, které se používá k vytvoření parametry funkce.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)