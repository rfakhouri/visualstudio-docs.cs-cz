---
title: "Zobrazit řetězce v vizualizéru řetězce | Microsoft Docs"
ms.custom: 
ms.date: 07/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 801618c900f11a562b42e610c56dfa7855dfaf39
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Zobrazení řetězců v vizualizéru řetězce v sadě Visual Studio
Při ladění, můžete otevřít vizualizéru řetězce na řetězce zobrazení, které jsou příliš dlouhé zobrazíte v okně data tip nebo ladicí program. V mnoha případech vizualizér můžete identifikovat poškozený řetězce.

Standardní předdefinovaný řetězec vizualizérech obsahovat prostý text, XML, HTML a JSON. Pro několik typů například WPF objekty, které se zobrazují v ladicím programu windows, jako **automobily** okno, můžete také otevřít vizualizérech.

## <a name="open-a-string-visualizer"></a>Otevřete vizualizéru řetězce

Chcete-li zobrazit prostý text, XML, HTML nebo JSON řetězec, klikněte na ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "vizualizér ikonu") při ukazatele myši na proměnné obsahující hodnotu řetězce. Je nutné v ladicím programu zobrazíte ikonu lupy pozastavena.

![Otevřete Vizualizéru řetězce](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>Zobrazení dat řetězců

**Výraz** pole v vizualizér řetězce zobrazuje aktuální proměnná nebo při přechodu myší nad výrazu v ladicím programu.

**Hodnotu** poli se zobrazí hodnotu řetězce. Vizualizér Text zobrazuje prostý text.

Prázdné **hodnota** označuje, že konkrétní vizualizér nemůže rozpoznat typ řetězec. Vizualizér XML příkladu prázdné **hodnotu** pro řetězec ve formátu jednoduchého textového řetězce (s žádné značky XML) nebo JSON. Pokud potřebujete zobrazit řetězec nelze rozpoznat v vizualizéru, použijte vizualizér text.

### <a name="view-json-string-data"></a>Zobrazení dat řetězce formátu JSON

Zobrazí podobně jako na následujícím obrázku v vizualizér JSON ve správném formátu řetězce formátu JSON. Nesprávný formát JSON se může zobrazovat ikona chyby (nebo při nerozpoznaný prázdný).

![Vizualizér řetězce JSON](../debugger/media/dbg-tips-string-visualizer-json.png "vizualizér řetězce formátu JSON")

### <a name="view-xml-string-data"></a>Zobrazení dat řetězců XML

Řetězec XML ve správném formátu se zobrazí podobná na následujícím obrázku v vizualizér XML. Poškozený obsah XML může zobrazit bez značky XML (nebo při nerozpoznaný prázdný).

![Vizualizér řetězce XML](../debugger/media/dbg-string-visualizers-xml.png "vizualizér řetězce XML")

### <a name="view-html-string-data"></a>Zobrazení HTML řetězcových dat.

Podobně jako zobrazení, že zobrazí se pokud řetězec je vykreslen v prohlížeči, jak je znázorněno na následujícím obrázku se zobrazí ve správném formátu řetězec HTML. Chybná HTML může zobrazit jako prostý text.

![Řetězec HTML vizualizér](../debugger/media/dbg-string-visualizers-html.png "vizualizér řetězec HTML")

## <a name="see-also"></a>Viz také  
 [Vytvořit vlastní Vizualizérech (C#, Visual Basic)](../debugger/create-custom-visualizers-of-data.md)