---
title: IDebugExpressionEvaluationCompleteEvent2::GetResult | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetResult
helpviewer_keywords:
- IDebugExpressionEvaluationCompleteEvent2::GetResult
ms.assetid: d9ad3e22-b6b2-421e-9a43-6bb8c70d12a9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a7ceb20932a0d41486675a8bf1928831726856cb
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200943"
---
# <a name="idebugexpressionevaluationcompleteevent2getresult"></a>IDebugExpressionEvaluationCompleteEvent2::GetResult
Získá výsledek vyhodnocení výrazu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetResult( 
   IDebugProperty2** ppResult
);
```

```csharp
int GetResult( 
   out IDebugProperty2 ppResult
);
```

## <a name="parameters"></a>Parametry
`ppResult` [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje výsledek vyhodnocení výrazu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vrácený [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt obsahuje hodnotu vyhodnocený výraz. Všimněte si, že tato hodnota může být složité hodnota jako například pole, ale konečný výsledek musí být číselný nebo řetězcová hodnota, která se zobrazí uživateli.

## <a name="see-also"></a>Viz také:
- [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)