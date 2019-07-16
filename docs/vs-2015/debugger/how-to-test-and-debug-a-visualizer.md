---
title: 'Postupy: Testování a ladění Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 18261d9e8c6c7d3f65dea7c72439b29f4e2e0df3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176493"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Postupy: Testování a ladění vizualizéru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jakmile jste napsali vizualizéru, budete muset ladění a testování.  
  
 Jedním ze způsobů k otestování vizualizéru je z hlediska instalace v sadě Visual Studio a jeho volání z okna ladicího programu. (Viz [jak: Instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).) Pokud to uděláte, musíte použít druhou instanci aplikace Visual Studio k připojení a ladění vizualizéru, který je spuštěn v první instanci ladicího programu.  
  
 Snadný způsob, jak ladit vizualizéru je spustit vizualizéru z testu ovladače. Rozhraní API vizualizéru usnadňují vytváření tento ovladač, která je volána *vizualizéru vývoj hostitele*.  
  
### <a name="to-create-a-visualizer-development-host"></a>Pokud chcete vytvořit hostitele vývoj vizualizéru  
  
1. Ve své třídě ladicí program side zahrnují statická metoda, která vytvoří <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> objektu a volá metodu jeho zobrazit:  
  
    ```  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       myHost.ShowVisualizer();  
    }  
    ```  
  
     Parametry použité k vytvoření hostitele je datový objekt, který se zobrazí ve vizualizátoru (`objectToVisualize`) a typ třídy na straně ladicího programu.  
  
2. Přidejte následující příkaz k volání `TestShowVisualizer`. Pokud jste vytvořili vaší vizualizéru v knihovně tříd, je potřeba vytvořit spustitelný soubor pro volání knihovny tříd a spustitelný soubor umístit tento příkaz:  
  
    ```  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
     Podrobnější příklad naleznete v tématu [názorný postup: Zápis Vizualizéru v C# ](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [Postupy: Instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Vytváření vlastních vizualizérů](../debugger/create-custom-visualizers-of-data.md)
