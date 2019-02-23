---
title: IDebugBinder3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3
helpviewer_keywords:
- IDebugBinder3 interface
ms.assetid: 92353a74-dc74-4f93-8762-61d6b220478c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 733ede7b7bad73419fc160f4c15b660b50b26b7e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707546"
---
# <a name="idebugbinder3"></a>IDebugBinder3
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní poskytuje přístup k typy, aliasy a služby vlastní vizualizér.

## <a name="syntax"></a>Syntaxe

```
IDebugBinder3 : IDebugBinder
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj implementuje toto rozhraní pro podporu aliasy, vlastní vizualizér služby a přístup k informacím o typu objektu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní získá pomocí tohoto rozhraní [QueryInterface](/cpp/atl/queryinterface).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod poskytovaných parametrem [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní, toto rozhraní implementuje následující:

|Metoda|Popis|
|------------|-----------------|
|[GetMemoryObject](../../../extensibility/debugger/reference/idebugbinder3-getmemoryobject.md)|Načte objekt paměti představující paměti, ke kterému je vázán tento objekt.|
|[GetExceptionObjectAndType](../../../extensibility/debugger/reference/idebugbinder3-getexceptionobjectandtype.md)|Načte výjimky přidružené k tomuto objektu (pokud existuje)|
|[FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)|Načte její název aliasu|
|[GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)|Načte pole všechny aliasy pro tento objekt|
|[GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)|Získá počet typů argumentů, které jsou přidružené k tomuto objektu|
|[GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)|Načte seznam typů argumentů, které jsou přidružené k tomuto objektu|
|[GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)|Získá rozhraní pro služby vizualizéru|
|[GetMemoryContext64](../../../extensibility/debugger/reference/idebugbinder3-getmemorycontext64.md)|Převede objekt umístění nebo adresu paměti 64-bit na místní paměti.|

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)