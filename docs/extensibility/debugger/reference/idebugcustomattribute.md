---
title: IDebugCustomAttribute | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute
helpviewer_keywords:
- IDebugCustomAttribute interface
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ae596c781d864f97087371fcb10595aa5f6a8ee9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346128"
---
# <a name="idebugcustomattribute"></a>IDebugCustomAttribute
Toto rozhraní představuje atribut vlastní a můžete zadat název, nadřazený a třídy typu atributu.

## <a name="syntax"></a>Syntaxe

```
IDebugCustomAttribute : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje toto rozhraní, aby bylo možné podporovat vlastní atributy přidružené k symbolu. Obvykle je implementované v jeho vlastní objekt.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [Další](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) vrátí toto rozhraní. Volání [enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) vrátí metoda [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugCustomAttribute`.

|Metoda|Popis|
|------------|-----------------|
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|Získá pole, ke kterému je připojený aktuální atribut.|
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|Získá typ vlastního atributu třídy.|
|[GetName](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|Získá název vlastního atributu.|
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|Získá informace o atributu jako objekt blob bajtů.|

## <a name="remarks"></a>Poznámky
 Vlastní atribut je struktura jazyka C#, který poskytuje vlastní metadata přidružená k dané třídy nebo metody.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)
- [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)