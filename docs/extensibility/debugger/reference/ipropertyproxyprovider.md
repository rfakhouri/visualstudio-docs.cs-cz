---
title: IPropertyProxyProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IPropertyProxyProvider
helpviewer_keywords:
- IPropertyProxyProvider interface
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f12925c362d3c87b6eb6724c28936333519e844f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53877095"
---
# <a name="ipropertyproxyprovider"></a>IPropertyProxyProvider
Toto rozhraní poskytuje proxy rozhraní pro zobrazení a změna data objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Chyba při vyhodnocování výrazu (EE) implementuje na stejný objekt, který implementuje toto rozhraní [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní jako součást EE pro podporu vizualizérů typů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProperty3` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 `IPropertyProxyProvider` Rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|Načte proxy rozhraním vlastnosti k zobrazení dat na objektu.|  
  
## <a name="remarks"></a>Poznámky  
 I když EE implementuje toto rozhraní, provádění [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) je obvykle zpracovávána [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md). Zobrazit [Visualizing a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti o získání rozhraní IEEVisualizerService.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [Vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)