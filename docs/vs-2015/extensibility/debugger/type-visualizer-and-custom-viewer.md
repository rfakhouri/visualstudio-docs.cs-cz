---
title: Typ Vizualizéru a vlastní prohlížeč | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a85be2978abe35e91096b55fba5ec5281be25fbe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185309"
---
# <a name="type-visualizer-and-custom-viewer"></a>Vizualizér typů a vlastní prohlížeč
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Typ vizualizéru je komponenta, která zobrazuje část dat ve velmi specifickém formátu. Tento formát je zcela v kompetenci implementátora vizualizéru, už to jsou koncového uživatele nebo jiného dodavatele vizualizéry.  
  
 Vlastní prohlížeč je součástí Chyba při vyhodnocování vlastní výraz, který zobrazuje část dat ve velmi specifickém formátu. Tento formát je zcela v kompetenci implementátora vlastní prohlížeč, což znamená, že formát až implementátora vyhodnocovací filtr výrazů (EE).  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>Podpora pro Vizualizérů typů v vyhodnocovače výrazů  
 EE můžete podpořit vizualizérů typů podporuje sadu rozhraní, které jsou přístupné pro vizualizátory: rozhraní, jako například [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) a [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Upozorňujeme, že EE nezodpovídá za implementace vizualizér typů samotné: EE pouze umožňuje vizualizéry externí přístup k jeho informace o typu. Takové vizualizéry může dodávaná EE a nainstalovaný na příslušné místo v sadě Visual Studio, zadán pomocí jiného dodavatele třetích stran nebo dokonce koncovým uživatelem.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>Podpora vlastních prohlížečů v vyhodnocovače výrazů  
 EE může také podporovat vlastních prohlížečů, ve kterých EE samotné poskytuje kód pro zobrazení datového typu. Implementuje vlastní prohlížeč [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) požadované rozhraní, která zpracovává všechny úkoly zobrazovat data v libovolné formát; má plnou kontrolu nad zobrazením v prohlížeči a můžete povolit i data, která mají být změněna. Žádné vlastních prohlížečů poskytovaných EE jsou dostupné EE při dodání produktu.  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)   
 [Chyba při vyhodnocování výrazu](../../extensibility/debugger/expression-evaluator.md)   
 [Ladicí stroj](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
