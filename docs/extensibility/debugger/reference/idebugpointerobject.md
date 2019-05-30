---
title: IDebugPointerObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject
helpviewer_keywords:
- IDebugPointerObject interface
ms.assetid: 257fa167-b46e-4ffb-9a12-272efbf26702
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c884f2794031d92add956bf4364824165ee1edfb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66343932"
---
# <a name="idebugpointerobject"></a>IDebugPointerObject
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní představuje ukazatel objektu.

## <a name="syntax"></a>Syntaxe

```
IDebugPointerObject : IDebugObject
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Chyba při vyhodnocování výrazu implementuje toto rozhraní k reprezentaci ukazatele objektu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní můžete získat pomocí tohoto rozhraní [QueryInterface](/cpp/atl/queryinterface) Pokud `IDebugObject` představuje ukazatel.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugPointerObject` rozhraní poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[Dereference](../../../extensibility/debugger/reference/idebugpointerobject-dereference.md)|Získá objekt, na kterou ukazuje rozhraní.|
|[GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)|Získá hodnotu, na kterou ukazuje rozhraní jako řadu bajtů po sobě jdoucích.|
|[SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)|Nastaví hodnotu, na kterou ukazuje rozhraní v řadě po sobě jdoucích bajtů.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní vyhodnocovače výrazů používá k zastoupení ukazatele v strom analýzy.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)