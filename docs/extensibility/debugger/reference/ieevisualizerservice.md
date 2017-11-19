---
title: IEEVisualizerService | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerService
helpviewer_keywords: IEEVisualizerService interface
ms.assetid: 3bdb124b-c582-47ba-b465-13c6a1cdb702
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 404dcdd61955a1d3ac37fc2206d1b0fdf79684f6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerservice"></a>IEEVisualizerService
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní implementuje klíče metody, které poskytují funkce [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) a [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEEVisualizerService : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní umožňuje (EE) pro podporu vizualizérech typ vyhodnocovací filtr výrazů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání EE [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md) k získání tohoto rozhraní jako součást jeho podporu pro typ vizualizérech.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)|Načte počet vlastní prohlížeče, o kterých se ví této služby.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)|Načte seznam vlastní prohlížeče.|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)|Vrátí objekt proxy pro vlastnost.|  
|[GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)|Načte počet řetězce hodnoty má být zobrazen pro zadanou vlastnost nebo pole.|  
  
## <a name="remarks"></a>Poznámky  
 Rozhraní IDE používá [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní k určení, zda neexistují žádné vlastní prohlížeče nebo zadejte vizualizérech pro vlastnost. Vytvořením vizualizér služby (s [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)), EE může poskytovat funkce pro `IDebugProperty3` a [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) (který podporuje zobrazení a změna Hodnota vlastnosti) rozhraní a za účelem podpory vizualizérech typu.  
  
 Pokud EE má vlastní prohlížeče která sama implementuje, můžete připojit EE `CLSID`s těmito vlastní prohlížeče na konec seznamu vrácených [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md). To umožňuje EE podporovat typ vizualizérech i vlastní vlastní prohlížeče. Právě ujistěte [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) odráží přidání všechny vlastní prohlížeče.  
  
 V tématu [vizualizér typ a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) diskuzi o rozdíl mezi vizualizérech a prohlížeče.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)   
 [Typ vizualizér a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)