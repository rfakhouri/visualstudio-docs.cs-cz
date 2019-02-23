---
title: IDebugExpressionEvaluator::Parse | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5a93d909fbc8882c5864097a2a36c36749327a2d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693911"
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
Tato metoda převede řetězec s výrazem na analyzovaný výrazu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Parse( 
   LPCOLESTR                upstrExpression,
   PARSEFLAGS               dwFlags,
   UINT                     nRadix,
   BSTR*                    pbstrError,
   UINT*                    pichError,
   IDebugParsedExpression** ppParsedExpression
);
```

```csharp
int Parse(
   string                     upstrExpression,
   enum_PARSEFLAGS            dwFlags,
   uint                       nRadix,
   out string                 pbstrError,
   out uint                   pichError,
   out IDebugParsedExpression ppParsedExpression
);
```

#### <a name="parameters"></a>Parametry
 `upstrExpression`

 [in] Řetězec výrazu, který má být analyzován.

 `dwFlags`

 [in] Kolekce [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) konstanty, které určují, jak má být analyzován výraz.

 `nRadix`

 [in] Základ, který se má použít pro interpretaci jakékoli číselné informace.

 `pbstrError`

 [out] Vrátí chybu jako čitelný text.

 `pichError`

 [out] Vrátí pozici znaku start Chyba v řetězci výraz.

 `ppParsedExpression`

 [out] Vrátí analyzovaný výrazu v [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda vytváří analyzovaný výrazu, nikoli skutečnou hodnotu. Analyzovaná výrazu je připraven k vyhodnocení, to znamená, převést na hodnotu.

## <a name="see-also"></a>Viz také
- [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)
- [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)
- [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)