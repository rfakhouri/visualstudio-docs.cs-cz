---
title: IDebugPropertyField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPropertyField
helpviewer_keywords:
- IDebugPropertyField interface
ms.assetid: b50edb2c-fb8d-4def-993d-17d23d2027c1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 52920de731a43b40355c1ca2821e2a86e7ef82b6
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458751"
---
# <a name="idebugpropertyfield"></a>IDebugPropertyField
Toto rozhraní poskytuje funkce, které umožňují načtení a nastavení vlastnosti.

## <a name="syntax"></a>Syntaxe

```
IDebugPropertyField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md). Toto rozhraní je jako specializaci té, která podporuje koncept vlastnosti třídy.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Použití [QueryInterface](/cpp/atl/queryinterface) získat z tohoto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí metoda `FIELD_KIND_PROP`.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)|Získá metody, která získá vlastnost.|
|[GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)|Získá metody, která nastaví vlastnost.|

## <a name="remarks"></a>Poznámky
 Vlastnost je koncept spravovaného kódu a představuje metodu, která je zpracovávána jako proměnnou. Vlastnosti v nespravované C++ neexistují.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)