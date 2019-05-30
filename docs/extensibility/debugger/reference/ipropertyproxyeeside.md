---
title: IPropertyProxyEESide | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide
helpviewer_keywords:
- IPropertyProxyEESide interface
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f6528b146ad3128dd880e594b25ebb5df88bb8f2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353444"
---
# <a name="ipropertyproxyeeside"></a>IPropertyProxyEESide
Toto rozhraní poskytuje metody pro zobrazení dat na související objekt. Toto rozhraní je součástí Podpora vizualizérů typů.

## <a name="syntax"></a>Syntaxe

```
IPropertyProxyEESide : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovače výrazů implementuje toto rozhraní pro podporu vizualizérů typů.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) získat toto rozhraní. Volání [QueryInterface](/cpp/atl/queryinterface) na [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní získat [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Toto rozhraní implementují následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|Inicializuje zprostředkovatele zdroje dat tak, aby data objektu přístupná.|
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|Načte informace o sestavení objektu.|
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|Získá počáteční data pro objekt.|
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|Vytvoří kopii stávající datové úložiště.|
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|Vytvoří odkaz na existující datové úložiště.|
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|Načte informace o konkrétní sestavení v kontextu sestavení obsahující tento objekt.|

## <a name="remarks"></a>Poznámky
 Typ vizualizéru používá pro přístup k hodnoty přidružené k objektu, který toto rozhraní je součástí tohoto rozhraní. K datům přistupuje prostřednictvím [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) rozhraní, která poskytuje zobrazení jen pro čtení dat.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [Vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)