---
title: Zadejte vlastní prohlížeče a vizualizér | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d419130cd93c6cc2f7dcff132fdafc8986bfd30a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126907"
---
# <a name="type-visualizer-and-custom-viewer"></a>Typ vizualizér a vlastní prohlížeč
Vizualizér typ je komponenta, která zobrazuje část dat ve velmi specifickém formátu. Tento formát, záleží zcela implementátor vizualizér, je-li jej koncového uživatele nebo jiného dodavatele třetích stran o vizualizérech.  
  
 Vlastní prohlížeč je součástí vyhodnocování vlastní výraz, který zobrazuje část dat ve velmi specifickém formátu. Tento formát, záleží zcela implementátor vlastní prohlížeče, což znamená, že formát není až implementátor vyhodnocovací filtr výrazů (EE).  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>Podpora pro typ Vizualizérech v vyhodnocení výrazu  
 EE podporují typ vizualizérech a podporuje sadu rozhraní, které jsou přístupné pro vizualizérech: rozhraní, jako [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) a [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Upozorňujeme však, že EE není zodpovědná za implementaci vizualizér typu, samotné: EE jenom umožňuje externí vizualizérech přístup k jeho informace o typu. Takové vizualizérech mohou být dodaný spolu s EE a nainstalovaný na příslušné místo v sadě Visual Studio, zadaný jiného dodavatele třetích stran nebo i koncovým uživatelem.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>Podpora pro vlastní prohlížečů v vyhodnocení výrazu  
 EE může také podporovat vlastní prohlížeče, ve kterých poskytuje EE samotný kód pro zobrazení datového typu. Implementuje vlastní prohlížeč [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) rozhraní, která zpracovává veškeré povinnosti zobrazující data v jakémkoli formátu se požaduje; prohlížeč má plnou kontrolu nad zobrazení a můžete povolit i data, která má být změněn. Všechny vlastní prohlížeče poskytl EE jsou součástí EE při dodání produktu.  
  
## <a name="see-also"></a>Viz také  
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)   
 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluator.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)