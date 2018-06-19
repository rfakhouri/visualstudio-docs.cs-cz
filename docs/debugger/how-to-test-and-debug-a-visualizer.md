---
title: 'Postupy: testování a ladění Vizualizéru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 860d6bd5f89ff85f3abf75f1beceb62b6b860d54
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476134"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Postupy: Testování a ladění vizualizéru
Jednou byly zapsány vizualizéru, budete muset ladění a testování.  
  
 Jedním ze způsobů k testování vizualizéru je instalace v sadě Visual Studio a volání z okna ladicího programu. (Viz [postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).) Pokud tak učiníte, musíte použít druhou instanci sady Visual Studio k připojení a ladění vizualizéru, který je spuštěn v první instance ladicího programu.  
  
 Snadný způsob, jak ladění vizualizéru je spustit vizualizér z testovací ovladače. Rozhraní API vizualizéru můžete snadno vytvořit tento ovladač, který se nazývá *vizualizér vývoj hostitele*.  
  
### <a name="to-create-a-visualizer-development-host"></a>Chcete-li vytvořit hostitele vývoj vizualizéru  
  
1.  Ve třídě ladicí program na straně zahrnují statickou metodu, která vytvoří <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> objektu a volá metodu jeho zobrazit:  
  
    ```  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       myHost.ShowVisualizer();  
    }  
    ```  
  
     Parametry použitý k vytvoření hostitele jsou datový objekt, který se zobrazí vizualizér (`objectToVisualize`) a typ třídy straně ladicí program.  
  
2.  Přidejte následující příkaz k volání `TestShowVisualizer`. Pokud jste vytvořili vaší vizualizér v knihovně tříd, budete muset vytvořit spustitelný soubor volání knihovny tříd a umístěte tento příkaz ve vašem spustitelný soubor:  
  
    ```  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
     Více kompletní příklad najdete v tématu [návod: zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Zápis Vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)