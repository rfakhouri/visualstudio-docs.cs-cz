---
title: Dialogové okno Vizualizéru řetězce | Dokumentace Microsoftu
ms.date: 10/10/2018
ms.custom: seoapril2019
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JavaScript
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 982db296fd17fb86b4a139e02a9418eeb507cd91
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366780"
---
# <a name="string-visualizer-dialog-box"></a>Dialogové okno vizualizéru řetězce

Při ladění v sadě Visual Studio, můžete zobrazit řetězce pomocí vizualizéru integrované řetězec. Vizualizér řetězce zobrazí řetězce, které jsou příliš dlouhé pro okno datový tip nebo ladicí program. Může také pomoct identifikovat poškozený řetězce.

Vizualizér integrované řetězec obsahuje prostý text, XML, HTML a JSON možnosti. Můžete také otevřít integrované vizualizéry pro několik dalších typů, jako [datové sady, datové tabulky a zobrazení DataView](../debugger/dataset-visualizer-dialog-box.md) objektů, z **automatické hodnoty** nebo dalších oknech ladicího programu.

> [!NOTE]
> Pokud je potřeba zkontrolovat prvky XAML nebo rozhraní WPF ve vizualizéru, najdete v článku nebo [vlastnosti kontrolovat XAML při ladění](../debugger/inspect-xaml-properties-while-debugging.md) nebo [použití vizualizéru stromu WPF](../debugger/how-to-use-the-wpf-tree-visualizer.md).

Otevřete vizualizéru řetězce, musí být pozastaveno během ladění. Podržte ukazatel myši nad proměnnou, která obsahuje prostý text, XML, HTML nebo JSON řetězcová hodnota a vyberte ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Vizualizéru ikonu").

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Výraz** poli se zobrazí proměnné nebo výrazu najedete.

**Hodnota** pole zobrazí hodnotu řetězce. Prázdnou hodnotu **hodnotu** znamená, že nemůže rozpoznat zvolené vizualizéru řetězce. Například **XML vizualizér** zobrazí prázdnou hodnotu **hodnotu** pro textový řetězec s žádné značky XML nebo řetězec formátu JSON. K zobrazení řetězce, které nemůže rozpoznat zvolené vizualizéru, zvolte **Vizualizátor textu** místo. **Vizualizátor textu** zobrazuje prostý text.

### <a name="json-string-data"></a>Data řetězce JSON

Podobně jako na následujícím obrázku v JSON visualizér se zobrazí řetězec JSON ve správném formátu. Nesprávný formát JSON se může zobrazit ikona chyby (nebo prázdné, pokud nebyl rozpoznán). K identifikaci chyby JSON, zkopírujte a vložte řetězec do nástroje linting JSON, jako [JSLint](https://www.jslint.com/).

![Vizualizér řetězce JSON](../debugger/media/dbg-tips-string-visualizer-json.png "vizualizéru řetězce JSON")

### <a name="xml-string-data"></a>Řetězcová data XML

Podobně jako na následujícím obrázku ve vizualizátoru XML se zobrazí řetězec XML ve správném formátu. Pokud nebyl rozpoznán se může zobrazit nesprávně vytvořeným kódem XML bez značek XML nebo prázdný.

![XML vizualizér řetězce](../debugger/media/dbg-string-visualizers-xml.png "XML vizualizér řetězce")

### <a name="html-string-data"></a>Data řetězce ve formátu HTML

Zobrazí se ve správném formátu řetězec ve formátu HTML jakoby vykreslení v prohlížeči, jak je znázorněno na následujícím obrázku. Poškozená HTML se může zobrazit jako prostý text.

![HTML vizualizér řetězce](../debugger/media/dbg-string-visualizers-html.png "HTML vizualizér řetězce")

## <a name="see-also"></a>Viz také:

- [Vytváření vlastních vizualizérů (C#, Visual Basic)](../debugger/create-custom-visualizers-of-data.md)
- [Vizualizace dat v sadě Visual Studio pro Mac](/visualstudio/mac/data-visualizations)