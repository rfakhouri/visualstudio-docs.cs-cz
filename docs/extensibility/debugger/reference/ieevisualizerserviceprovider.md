---
title: IEEVisualizerServiceProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerServiceProvider
helpviewer_keywords: IEEVisualizerServiceProvider interface
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4bd55bb42f902bcda7cdef1ea28a8d1c39d96f26
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerserviceprovider"></a>IEEVisualizerServiceProvider
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní umožňuje přístup na metodu, která můžete vytvořit vizualizér služby, která slouží ke zpracování typu vizualizér úlohy pro rozhraní IDE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEEVisualizerServiceProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní k vytvoření objektu služby vizualizér, které se pak použije k poskytování ID tříd (`CLSID`s) z typu vizualizérech k prostředí Visual Studio IDE.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Vyhodnocení výrazu (EE) volá [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md) k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|Vytvoří službu vizualizéru|  
  
## <a name="remarks"></a>Poznámky  
 `IEEVisualizerServiceProvider` Rozhraní je získané při provádění [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). Vizualizér služby, který vytvoří tohoto rozhraní slouží k poskytování funkce [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní, která je zodpovědná za implementaci EE. EE zodpovídá taky za implementaci [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) rozhraní, které umožňuje typ vizualizérech zobrazovat a upravovat vlastnosti na hodnotu.  
  
 V tématu [Visualizing a zobrazení Data](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti o interakci tato rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)