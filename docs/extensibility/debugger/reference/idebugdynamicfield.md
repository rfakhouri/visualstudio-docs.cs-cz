---
title: IDebugDynamicField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDynamicField
helpviewer_keywords:
- IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d94a685b9c79069a047e32155234f9bf6a50d5c5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875387"
---
# <a name="idebugdynamicfield"></a>IDebugDynamicField
Toto rozhraní představuje typ proměnné.

## <a name="syntax"></a>Syntaxe

```
IDebugDynamicField : IDebugField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno poskytovateli symbol jako základní třída pro libovolný typ, který může být stanovena v době běhu. Toto je pouze pro spravovaný kód.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Toto rozhraní představuje základní třídu, ze kterého mohou být odvozeny více specializované rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Toto rozhraní neposkytuje všechny metody kromě těch zděděných z `IDebugField`.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)