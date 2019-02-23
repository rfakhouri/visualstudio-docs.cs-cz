---
title: IEnumDebugPropertyInfo2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPropertyInfo2
helpviewer_keywords:
- IEnumDebugPropertyInfo2
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0fb43da8cf5d9ce361dd3eeff2a76b2ed092e67e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714930"
---
# <a name="ienumdebugpropertyinfo2"></a>IEnumDebugPropertyInfo2
Vytvoří výčet toto rozhraní [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugPropertyInfo2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní ke znázornění informací pro určité vlastnosti.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) získat toto rozhraní představující podřízené určité vlastnosti. Volání [enumproperties –](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) získat toto rozhraní představující vlastnosti konkrétní rámec zásobníku.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugPropertyInfo2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|Načte zadaný počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v sekvenci výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|Vynechá zadaný počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|Získá počet [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury v enumerátor.|

## <a name="remarks"></a>Poznámky
 Obecně platí je vlastnost hierarchie informace, které mohou zahrnovat název, hodnotu, adresy a typ, stejně jako všechny ostatní informace, třeba přidružené vlastnosti objektu nebo zásobníku rámce. Zobrazit [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) další podrobnosti.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
- [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)