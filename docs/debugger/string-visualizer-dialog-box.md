---
title: Zobrazit řetězců ve vizualizéru řetězce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 07/11/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6e4519a85659b36e5cf6baebaadd1d1c626f1a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151031"
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Zobrazení řetězců ve vizualizéru řetězce v sadě Visual Studio
Při ladění, můžete otevřít vizualizéru řetězce na řetězce zobrazení, které jsou příliš dlouhé, chcete-li zobrazit v okně datového tipu nebo ladicí program. V mnoha případech vizualizéru vám mohou pomoci při identifikaci poškozený řetězců.

Standardní integrované řetězec vizualizéry zahrnují prostý text, XML, HTML a JSON. Pro několik typů, jako je například WPF objekty, které se zobrazí v ladicím programu, jako jsou windows **automatické hodnoty** okna, můžete také otevřít vizualizéry.

## <a name="open-a-string-visualizer"></a>Otevřete vizualizéru řetězce

Chcete-li zobrazit prostý text, XML, HTML nebo JSON řetězec, klikněte na ikonu lupy ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Vizualizéru ikonu") při najetí myší nad proměnné obsahující hodnotu řetězce. Je nutné pozastavit v ladicím programu zobrazíte ikonu lupy.

![Otevřete Vizualizéru řetězce](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>Řetězec dat zobrazení

**Výraz** pole ve vizualizéru řetězce zobrazuje aktuální proměnné nebo výrazu přechodu myši nad v ladicím programu.

**Hodnotu** pole zobrazí hodnotu řetězce. Vizualizátor textu zobrazuje prostý text.

Prázdnou hodnotu **hodnotu** označuje, že konkrétní vizualizér nelze rozpoznat typ string. XML vizualizér příkladu prázdnou hodnotu **hodnotu** pro řetězec ve formátu prostého textu řetězec (s žádné značky XML) nebo JSON. Pokud potřebujete zobrazit ve vizualizéru nerozpoznatelný řetězce, pomocí nástroje text visualizer.

### <a name="view-json-string-data"></a>Data řetězce JSON zobrazení

Zobrazí podobně jako na následujícím obrázku v JSON visualizér řetězec JSON ve správném formátu. Nesprávný formát JSON se může zobrazit ikona chyby (nebo prázdné, pokud nebyl rozpoznán). Pokud se zobrazí ikona chyby, zkopírujte a vložte řetězec formátu JSON, jako do nástroje JSON linting [JSLint](https://www.jslint.com/) k identifikaci chyba JSON.

![Vizualizér řetězce JSON](../debugger/media/dbg-tips-string-visualizer-json.png "Vizualizéru řetězce JSON")

### <a name="view-xml-string-data"></a>Zobrazení dat řetězec XML

Řetězec ve správném formátu XML se zobrazí podobně jako na následujícím obrázku v XML vizualizér. Bez značky XML (nebo prázdné, pokud nebyl rozpoznán) se může zobrazit nesprávně vytvořeným kódem XML.

![XML vizualizér řetězce](../debugger/media/dbg-string-visualizers-xml.png "XML vizualizér řetězce")

### <a name="view-html-string-data"></a>Data řetězce zobrazení HTML

Podobně jako zobrazení, že zobrazí se pokud řetězec je vykreslen v prohlížeči, jak je znázorněno na následujícím obrázku se zobrazí ve správném formátu řetězec HTML. Poškozená HTML se může zobrazit jako prostý text.

![Řetězec HTML vizualizér](../debugger/media/dbg-string-visualizers-html.png "řetězec ve formátu HTML vizualizér")

## <a name="see-also"></a>Viz také  
 [Vytváření vlastních Vizualizérů (C#, Visual Basic)](../debugger/create-custom-visualizers-of-data.md)