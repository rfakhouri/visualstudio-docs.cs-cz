---
title: IEEVisualizerDataProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider
helpviewer_keywords:
- IEEVisualizerDataProvider interface
ms.assetid: 5fdfe6e3-b94e-4edb-acc5-41d8773d8ca5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a4a070c17760ea8cf004b1fcc733f7fe38760db7
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223939"
---
# <a name="ieevisualizerdataprovider"></a>IEEVisualizerDataProvider
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní umožňuje změnit hodnoty objektu prostřednictvím vizualizér typů.

## <a name="syntax"></a>Syntaxe

```
IEEVisualizerDataProvider : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Chyba při vyhodnocování výrazu implementuje toto rozhraní pro podporu změny dat na vlastnost objektu prostřednictvím vizualizér typů.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Toto rozhraní je použité při vytváření [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) objektu přímo pomocí volání [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Zobrazit [Visualizing a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md) další podrobnosti.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí

|Metoda|Popis|
|------------|-----------------|
|[CanSetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-cansetobjectforvisualizer.md)|Určuje, zda je možné aktualizovat objektu (a následně jeho hodnotu), který představuje tento vizualizér.|
|[GetNewObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer.md)|Pro tento vizualizátor Vynutí opakované vyhodnocení objektu.|
|[GetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getobjectforvisualizer.md)|Získá existující objekt pro tento vizualizátor (žádné vyhodnocení se provádí).|
|[SetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer.md)|Aktualizuje objekt pro tento vizualizátor, a tím změnit hodnotu, kterou představuje vizualizér.|

## <a name="remarks"></a>Poznámky
 Služby visualizéru (představované výrazem [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) rozhraní a vrácené [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)) udržuje odkaz na objekt implementace `IEEVisualizerDataProvider` rozhraní . V důsledku toho `IEEVisualizerDataProvider` rozhraní by neměl být implementováno na stejný objekt, který implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Pokud tento objekt uchovává odkaz na `IEEVisualizerService` objektu: cyklický odkaz výsledky a zablokování dochází tehdy, když objekty jsou zničeny. Doporučený postup je pro implementaci `IEEVisualizerDataProvider` na samostatný objekt, ke kterému `IDebugProperty2` objektu delegáti bez volání `IUnknown::AddRef` na něm.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)
- [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)
- [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)