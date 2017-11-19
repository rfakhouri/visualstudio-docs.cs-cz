---
title: IPropertyProxyProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyProvider
helpviewer_keywords: IPropertyProxyProvider interface
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: de400fc9e5b631a7ccffb0547fa693a8bf0ac419
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ipropertyproxyprovider"></a>IPropertyProxyProvider
Toto rozhraní poskytuje proxy rozhraní k zobrazení a změna dat objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje vyhodnocovací filtr výrazů (EE) pro stejný objekt, který implementuje [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní jako součást EE podpoře vizualizérech typu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugProperty3` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 `IPropertyProxyProvider` Rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|Načte vlastnost proxy rozhraní k zobrazení dat na objekt.|  
  
## <a name="remarks"></a>Poznámky  
 I když EE implementuje toto rozhraní, provádění [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) je obvykle zpracovávány [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md). V tématu [Visualizing a zobrazení Data](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti o získání rozhraní IEEVisualizerService.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [Typ vizualizér a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)