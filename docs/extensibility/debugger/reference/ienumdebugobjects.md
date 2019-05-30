---
title: IEnumDebugObjects | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dea4b4781fd8026c29436bbd37a6bfa6824e73b3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66339485"
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Představuje kolekci objektů implementace tohoto rozhraní [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugObjects : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Chyba při vyhodnocování výrazu implementuje toto rozhraní k poskytování sady objektů, které implementují [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní. Všimněte si, že to není standardní výčet COM z důvodu přítomnosti [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md) metody.

## <a name="notes-for-callers"></a>Poznámky pro volající
- [Metody GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md) vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Toto rozhraní implementuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|Načte další sadu [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekty z výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|Vynechá zadaný počet položek.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|Obnoví výčtu první položka.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|Načte kopii do aktuálního výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|Získá počet položek ve výčtu.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní podporuje ladicí stroj, jak vytvořit výčet sadu objektů v poli.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)