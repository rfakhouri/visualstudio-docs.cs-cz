---
title: 'Postupy: testování a ladění Vizualizéru | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9972951b1c5064fcc0582909976a234158ea096
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676083"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Postupy: Testování a ladění vizualizéru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: testování a ladění Vizualizéru](https://docs.microsoft.com/visualstudio/debugger/how-to-test-and-debug-a-visualizer).  
  
Jakmile jste napsali vizualizéru, budete muset ladění a testování.  
  
 Jedním ze způsobů k otestování vizualizéru je z hlediska instalace v sadě Visual Studio a jeho volání z okna ladicího programu. (Viz [postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).) Pokud to uděláte, musíte použít druhou instanci aplikace Visual Studio k připojení a ladění vizualizéru, který je spuštěn v první instanci ladicího programu.  
  
 Snadný způsob, jak ladit vizualizéru je spustit vizualizéru z testu ovladače. Rozhraní API vizualizéru usnadňují vytváření tento ovladač, která je volána *vizualizéru vývoj hostitele*.  
  
### <a name="to-create-a-visualizer-development-host"></a>Pokud chcete vytvořit hostitele vývoj vizualizéru  
  
1.  Ve své třídě ladicí program side zahrnují statická metoda, která vytvoří <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> objektu a volá metodu jeho zobrazit:  
  
    ```  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       myHost.ShowVisualizer();  
    }  
    ```  
  
     Parametry použité k vytvoření hostitele je datový objekt, který se zobrazí ve vizualizátoru (`objectToVisualize`) a typ třídy na straně ladicího programu.  
  
2.  Přidejte následující příkaz k volání `TestShowVisualizer`. Pokud jste vytvořili vaší vizualizéru v knihovně tříd, je potřeba vytvořit spustitelný soubor pro volání knihovny tříd a spustitelný soubor umístit tento příkaz:  
  
    ```  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
     Podrobnější příklad naleznete v tématu [návod: zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)



