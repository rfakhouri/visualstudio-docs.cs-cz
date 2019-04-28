---
title: 'Postupy: Testování a ladění Vizualizéru | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f0353234e5a266ca1a344ce7bc304f27d8c3af95
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62906281"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Postupy: Testování a ladění Vizualizéru
Jakmile jste napsali vizualizéru, budete muset ladění a testování.

Jedním ze způsobů k otestování vizualizéru je z hlediska instalace v sadě Visual Studio a jeho volání z okna ladicího programu. (Viz [jak: Instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md).) Pokud to uděláte, musíte použít druhou instanci aplikace Visual Studio k připojení a ladění vizualizéru, který je spuštěn v první instanci ladicího programu.

Snadný způsob, jak ladit vizualizéru je spustit vizualizéru z testu ovladače. Rozhraní API vizualizéru usnadňují vytváření tento ovladač, která je volána *vizualizéru vývoj hostitele*.

### <a name="to-create-a-visualizer-development-host"></a>Pokud chcete vytvořit hostitele vývoj vizualizéru

1. Ve své třídě ladicí program side zahrnují statická metoda, která vytvoří <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> objektu a volá metodu jeho zobrazit:

    ```csharp
    public static void TestShowVisualizer(object objectToVisualize)
    {
        VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));
        myHost.ShowVisualizer();
    }
    ```

    Parametry použité k vytvoření hostitele je datový objekt, který se zobrazí ve vizualizátoru (`objectToVisualize`) a typ třídy na straně ladicího programu.

2. Přidejte následující příkaz k volání `TestShowVisualizer`. Pokud jste vytvořili vaší vizualizéru v knihovně tříd, je potřeba vytvořit spustitelný soubor pro volání knihovny tříd a spustitelný soubor umístit tento příkaz:

    ```csharp
    DebuggerSide.TestShowVisualizer(myString);
    ```

    Podrobnější příklad naleznete v tématu [názorný postup: Zápis Vizualizéru v C# ](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).

## <a name="see-also"></a>Viz také
- [Návod: Zápis vizualizéru v jazyce C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)
- [Postupy: Instalace vizualizéru](../debugger/how-to-install-a-visualizer.md)
- [Vytváření vlastních vizualizérů](../debugger/create-custom-visualizers-of-data.md)
