---
title: IDebugAlias | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias
helpviewer_keywords:
- IDebugAlias interface
ms.assetid: 3cc4c9a4-7805-4239-b00e-eb4a024f3c55
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 793b57c217144f04dc573b98d58dea9d9202995c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63414193"
---
# <a name="idebugalias"></a>IDebugAlias
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Představuje číselná aliasu pro proměnnou. Alias je jednoduše jiný název proměnné.

## <a name="syntax"></a>Syntaxe

```
IDebugAlias : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Chyba při vyhodnocování výrazu (EE) implementuje toto rozhraní pro podporu číselné aliasy pro proměnné.

## <a name="notes-for-callers"></a>Poznámky pro volající
- [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) vytvoří alias pro daný objekt. Chcete-li vyhledat aliasy, použijte [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md) nebo [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Tyto metody jsou definované v `IDebugAlias` rozhraní.

|Metoda|Popis|
|------------|-----------------|
|[GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)|Získá objekt, na který odkazuje tento alias.|
|[GetName](../../../extensibility/debugger/reference/idebugalias-getname.md)|Získá název aliasu.|
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugalias-geticordebugvalue.md)|Načte `ICorDebugValue` rozhraní, které poskytuje přístup ke spravované kódu informace o tomto objektu (pouze pro spravovaný kód).|
|[Dispose](../../../extensibility/debugger/reference/idebugalias-dispose.md)|Označuje to, alias jako již nejsou déle používány.|

## <a name="remarks"></a>Poznámky
 Desetinné číslo ve formátu řetězce následované znakem #, například 1001# je alias.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)
- [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)
- [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)