---
title: 'Postupy: Použití SDK značek Vizualizéru souběžnosti | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 19a45032-f8a7-4137-890e-2ceeec938b8d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a486c275c16a52bda937abab28828ff841f6e4c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54921905"
---
# <a name="how-to-use-the-concurrency-visualizer-markers-sdk"></a>Postupy: Použití SDK značek Vizualizéru souběžnosti
Toto téma ukazuje, jak použít sada Vizualizátor souběžnosti SDK k vytvoření rozsahy a napsat příznaky, zprávy a upozornění.  
  
### <a name="to-use-c"></a>Použití jazyka C++  
  
1.  Přidání podpory sada Vizualizátor souběžnosti SDK do vaší aplikace. Další informace najdete v tématu [sada Vizualizátor souběžnosti SDK](../profiling/concurrency-visualizer-sdk.md).  
  
2.  Přidat `include` příkazu a `using` příkazu pro sadu SDK.  
  
    ```C++  
  
    #include <cvmarkersobj.h>  
    using namespace Concurrency::diagnostic;  
  
    ```  
  
3.  Přidejte kód pro vytvoření tři rozsahy v řadě výchozí značky a zápis příznak, zprávy a upozornění, jeden pro každý rozsah. Členové jsou metody zapsat příznaky, zprávy a upozornění [marker_series](../profiling/marker-series-class.md) třídy. Konstruktor pro [span](../profiling/span-class.md) vyžaduje třídu `marker_series` objektu tak, aby každý rozsah je přidružený k konkrétní značky řady. A `span` končí, když se odstraní.  
  
    ```C++  
  
    marker_series series;  
    span *flagSpan = new span(series, 1, _T("flag span"));  
    series.write_flag(_T("Here is the flag."));  
    delete flagSpan;  
  
    span *messageSpan = new span(series, 2, _T("message span"));  
    series.write_flag(_T("Here is the message."));  
    delete messageSpan;  
  
    span *alertSpan = new span(series, 3, _T("alert span"));  
    series.write_flag(_T("Here is the alert."));  
    delete alertSpan;  
  
    ```  
  
4.  V panelu nabídky zvolte **analyzovat**, **Vizualizátor souběžnosti**, **spustit s aktuálním projektem** spusťte aplikaci a zobrazte Vizualizátor souběžnosti. Následující obrázek znázorňuje tři rozsahy a tři značky ve vizualizátoru souběžnosti.  
  
     ![Vizualizátor souběžnosti se 3 značkami a výstrahy](../profiling/media/cvmarkersnative.png "CvMarkersNative")  
  
5.  Přidejte kód k vytvoření další, vlastní značky řady zavoláním konstruktoru pro `marker_series` , která přebírá řetězec název řady, značky.  
  
    ```C++  
  
    marker_series flagSeries(_T("flag series"));  
    span *flagSeriesSpan = new span(flagSeries, 1, _T("flag span"));  
    flagSeries.write_flag(1, _T("flag"));  
    // Sleep to even out the display in the Concurrency Visualizer.  
    Sleep(50);  
    delete flagSeriesSpan;  
  
    marker_series messageSeries(_T("message series"));  
    span *messageSeriesSpan = new span(messageSeries, 1, _T("message span"));  
    messageSeries.write_message(1, _T("message"));  
    // Sleep to even out the display in the Concurrency Visualizer.  
    Sleep(50);  
    delete messageSeriesSpan;  
  
    ```  
  
6.  Spuštění aktuálního projektu zobrazíte Vizualizátor souběžnosti. Řada dvě značky se zobrazí v jejich vlastní procesu v zobrazení vláken. Následující obrázek znázorňuje dvě nové rozpětí.  
  
     ![Vizualizátor souběžnosti s 3 vlastní značky řady](../profiling/media/cvmarkerseriesnative.png "CvMarkerSeriesNative")  
  
### <a name="to-use-visual-basic-or-c"></a>Použití jazyka Visual Basic nebo C# #
  
1.  Přidání podpory sada Vizualizátor souběžnosti SDK do vaší aplikace. Další informace najdete v tématu [sada Vizualizátor souběžnosti SDK](../profiling/concurrency-visualizer-sdk.md).  
  
2.  Přidat `using` nebo `Imports` příkazu pro sadu SDK.  
  
    ```VB  
    Imports Microsoft.ConcurrencyVisualizer.Instrumentation  
  
    ```  
  
    ```csharp  
    using Microsoft.ConcurrencyVisualizer.Instrumentation;  
    ```  
  
3.  Přidejte kód pro vytvoření tři rozsahy na výchozí značky řadu a zápis příznak, zprávy a upozornění, jeden pro každý rozsah. Vytváření <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Span> objektu voláním statické `EnterSpan` metody. Zapsat do výchozí řadu, použijete metody statický zápis <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers> třídy.  
  
    ```VB  
  
    Dim flagSpan As Span = Markers.EnterSpan("flag span")  
    Markers.WriteFlag("Here is the flag.")  
    flagSpan.Leave()  
  
    Dim messageSpan As Span = Markers.EnterSpan("message span")  
    ' Sleep for a millisecond to even out the display in the Concurrency Visualizer.  
    System.Threading.Thread.Sleep(1)  
    Markers.WriteMessage("Here is a message")  
    messageSpan.Leave()  
  
    Dim alertSpan As Span = Markers.EnterSpan("alert span")  
    ' Sleep for a millisecond to even out the display in the Concurrency Visualizer.  
    System.Threading.Thread.Sleep(1)  
    Markers.WriteAlert("Here is an alert")  
    alertSpan.Leave()  
  
    ```  
  
    ```csharp  
  
    Span flagSpan = Markers.EnterSpan("flag span");  
    Markers.WriteFlag("Here is the flag.");  
    flagSpan.Leave();  
  
    Span messageSpan = Markers.EnterSpan("message span");  
    // Sleep for a millisecond to even out the display in the Concurrency Visualizer.  
    System.Threading.Thread.Sleep(1);  
    Markers.WriteMessage("Here is a message");  
    messageSpan.Leave();  
  
    Span alertSpan = Markers.EnterSpan("alert span");  
    // Sleep for a millisecond to even out the display in the Concurrency Visualizer.  
    System.Threading.Thread.Sleep(1);  
    Markers.WriteAlert("Here is an alert");  
    alertSpan.Leave();  
    ```  
  
4.  V panelu nabídky zvolte **analyzovat**, **Vizualizátor souběžnosti**, **spustit s aktuálním projektem** spusťte aplikaci a zobrazte Vizualizátor souběžnosti. Následující obrázek znázorňuje tři rozsahy a značkami tři v zobrazení vláken vizualizátoru souběžnosti.  
  
     ![Vizualizátor souběžnosti pomocí značek a výstrah](../profiling/media/cvmarkersmanaged.png "CvMarkersManaged")  
  
5.  Přidejte kód k vytvoření značky řadu zákazníků pomocí statické <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers.CreateMarkerSeries%2A> metody. <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.MarkerSeries> Třída obsahuje metody pro rozsahy a zapíše příznaky, zprávy a upozornění.  
  
    ```VB  
  
    Dim flagSeries As MarkerSeries = Markers.DefaultWriter.CreateMarkerSeries("flag series")  
    Dim flagSeriesSpan As Span = flagSeries.EnterSpan("flag span")  
    System.Threading.Thread.Sleep(1)  
    flagSeries.WriteFlag(1, "flag")  
    System.Threading.Thread.Sleep(1)  
    flagSeriesSpan.Leave()  
  
    Dim messageSeries As MarkerSeries = Markers.DefaultWriter.CreateMarkerSeries("message series")  
    Dim messageSeriesSpan As Span = messageSeries.EnterSpan("message span")  
    messageSeries.WriteMessage("message")  
    System.Threading.Thread.Sleep(1)  
    messageSeriesSpan.Leave()  
    ```  
  
    ```csharp  
  
    MarkerSeries flagSeries = Markers.DefaultWriter.CreateMarkerSeries("flag series");  
    Span flagSeriesSpan = flagSeries.EnterSpan("flag span");  
    System.Threading.Thread.Sleep(1);  
    flagSeries.WriteFlag(1, "flag");  
    System.Threading.Thread.Sleep(1);  
    flagSeriesSpan.Leave();  
  
    MarkerSeries messageSeries = Markers.DefaultWriter.CreateMarkerSeries("message series");  
    Span messageSeriesSpan = messageSeries.EnterSpan("message span");  
    messageSeries.WriteMessage("message");  
    System.Threading.Thread.Sleep(1);  
    messageSeriesSpan.Leave();  
    ```  
  
6.  Spuštění aktuálního projektu zobrazíte Vizualizátor souběžnosti. Tři značky řady se zobrazí v jejich vlastním procesu v zobrazení vláken. Následující obrázek znázorňuje tři nové rozpětí.  
  
     ![Vizualizátor souběžnosti s 3 vlastní značky řady](../profiling/media/cvmarkerseriesmanaged.png "CvMarkerSeriesManaged")  
  
## <a name="see-also"></a>Viz také:  
 [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)
