---
title: IDebugEnumField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField
helpviewer_keywords:
- IDebugEnumField interface
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4e2bcb8f8562b5b20231879d46c64eb73af027f0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920242"
---
# <a name="idebugenumfield"></a>IDebugEnumField
Toto rozhraní představuje typ výčtu.

## <a name="syntax"></a>Syntaxe

```
IDebugEnumField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje toto rozhraní představující výčet.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Použití [QueryInterface](/cpp/atl/queryinterface) získat z tohoto rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí `FIELD_TYPE_ENUM`.

## <a name="methods-in-vtable-order"></a>Metody v tabulce VTable pořadí
 Kromě metod na `IDebugField` a `IDebugContainerField` rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) popisující název pro tento typ výčtu.|
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|Vrátí název spojeného s danou hodnotou konstanty výčtu.|
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|Vrátí hodnotu přidruženou k názvu konstantní daný výčet|
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|Vrátí hodnotu přidruženou k dané výčtu konstant názvem, ale bez rozlišování případů.|

## <a name="remarks"></a>Poznámky
 Je základní symbol, který je ve skutečnosti vázané na umístění s [svázat](../../../extensibility/debugger/reference/idebugbinder-bind.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)