---
title: "Implementace typ Vizualizérech a vlastní prohlížeče | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: abef18c0-8272-4451-b82a-b4624edaba7d
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 19718425df6f0c8a656db0e3d7ebf0f06937f780
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-type-visualizers-and-custom-viewers"></a>Implementace typ Vizualizérech a vlastní prohlížečů
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Typ vizualizérech a vlastní prohlížeče umožnit uživateli zobrazení dat určitého typu způsobem, který je větší smysl než výpis jednoduché hexadecimální číslice. (EE) vyhodnocovací filtr výrazů můžete přidružit konkrétní typy dat nebo proměnné vlastní prohlížeče. Tato vlastní prohlížeče jsou implementované EE. EE může také podporovat externí typ vizualizérech, které mohou pocházet z jiného dodavatele třetích stran nebo i koncového uživatele.  
  
## <a name="discussion"></a>Diskusní  
  
### <a name="type-visualizers"></a>Typ Vizualizérech  
 Visual Studio se zobrazí seznam typ vizualizérech a vlastní prohlížečů pro každý objekt, který se má zobrazit v okně Sledování. (EE) vyhodnocovací filtr výrazů poskytuje seznam, pro každý typ, pro kterou chce podporovat typ vizualizérech a vlastní prohlížeče. Volání [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) a [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) spustit celý proces přístup k typu vizualizérech a vlastní prohlížeče (najdete v části [Visualizing a zobrazení Data](../../extensibility/debugger/visualizing-and-viewing-data.md)podrobnosti o volací sekvence).  
  
### <a name="custom-viewers"></a>Vlastní prohlížečů  
 Vlastní prohlížečů jsou implementované v EE pro konkrétní datový typ a jsou reprezentována [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) rozhraní. Vlastní prohlížeč není tak účinná jako typ vizualizéru, protože je k dispozici jenom v případě, že je prováděna EE, který implementuje tuto konkrétní vlastní prohlížeč. Implementace vlastních prohlížeč je jednodušší než implementace podporu pro typ vizualizérech. Však podpora typ vizualizérech poskytuje maximální flexibilitu pro koncového uživatele pro vizualizaci nebo jeho data. Zbývající část Tato diskuse se týká pouze typ vizualizérech.  
  
## <a name="interfaces"></a>Rozhraní  
 EE implementuje následující rozhraní pro podporu vizualizérech typ, který se má používat Visual Studio:  
  
-   [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)  
  
-   [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md)  
  
-   [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md)  
  
-   [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md)  
  
-   [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md)  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
 EE využívá následující rozhraní pro podporu vizualizérech typu:  
  
-   [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)  
  
-   [IEEVisualizerServiceProvider](../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)  
  
-   [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md)  
  
## <a name="see-also"></a>Viz také  
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Vizualizace a zobrazení dat](../../extensibility/debugger/visualizing-and-viewing-data.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)