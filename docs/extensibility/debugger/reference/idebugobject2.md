---
title: IDebugObject2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2
helpviewer_keywords:
- IDebugObject2 interface
ms.assetid: ef640967-8adb-4793-994d-ae1736510891
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d3f027fd08c38433d5f1357e56d90df96e223854
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317254"
---
# <a name="idebugobject2"></a>IDebugObject2
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní poskytuje další informace o objektu.

## <a name="syntax"></a>Syntaxe

```
IDebugObject2 : IDebugObject
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Chyba při vyhodnocování výrazu implementuje toto rozhraní nabízí podporu pro aliasy a přístup k informacím o objektu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní můžete získat pomocí tohoto rozhraní [QueryInterface](/cpp/atl/queryinterface). Navíc [GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md) vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní, `IDebugObject2` rozhraní implementuje následující:

|Metoda|Popis|
|------------|-----------------|
|[GetBackingFieldForProperty](../../../extensibility/debugger/reference/idebugobject2-getbackingfieldforproperty.md)|Získá pole nebo proměnné (pokud existuje), který může být zálohování vlastnost reprezentovaný tímto objektem.|
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugobject2-geticordebugvalue.md)|Získá objekt spravovaný kód představující hodnotu tohoto objektu.|
|[CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)|Vytvoří jedinečné ID pro tento objekt nebo vrátí existující alias.|
|[GetAlias](../../../extensibility/debugger/reference/idebugobject2-getalias.md)|Získá alias přidružené k tomuto objektu, pokud existuje.|
|[GetField](../../../extensibility/debugger/reference/idebugobject2-getfield.md)|Získá typ tohoto objektu.|
|[IsUserData](../../../extensibility/debugger/reference/idebugobject2-isuserdata.md)|Určuje, zda tento objekt představuje uživatelská data.|
|[IsEncOutdated](../../../extensibility/debugger/reference/idebugobject2-isencoutdated.md)|Určuje, zda stav funkce upravit a pokračovat již není platný.<br /><br /> Vyhodnocovací filtr vlastních výrazů neimplementuje této metody (vždy by měl vrátit `E_NOTIMPL`).|

## <a name="remarks"></a>Poznámky
 Zobrazit [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) diskuse o aliasy.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)
- [GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)