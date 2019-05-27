---
title: IDebugExpressionEvaluator::SetLocale | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator::SetLocale
helpviewer_keywords:
- IDebugExpressionEvaluator::SetLocale method
ms.assetid: d3d2027d-74e2-4ae6-bcc7-59d12f873b7c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9d92eb956105c310d251d6a8e85e61c70a66636a
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200868"
---
# <a name="idebugexpressionevaluatorsetlocale"></a>IDebugExpressionEvaluator::SetLocale
Tato metoda nastaví jazyk, který chcete použít k vytvoření tisknutelný výsledky.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetLocale( 
   WORD wLangID
);
```

```csharp
int SetLocale(
   ushort wLangID
);
```

## <a name="parameters"></a>Parametry
`wLangID`\
[in] Identifikátor jazyka.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda může být volána v mnoha případech vyhodnocovací filtr výrazů (EE) je načten, proto musí být EE přepínat jazyky v reálném čase. EE používá k vrácení chybové zprávy a řetězce v jazyce vhodném toto národní prostředí.

## <a name="see-also"></a>Viz také:
- [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)