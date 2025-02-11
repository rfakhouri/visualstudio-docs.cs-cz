---
title: Sada Vizualizátor souběžnosti SDK | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.sdk.about
ms.assetid: 4b22cdf9-59b1-4c88-a6d8-1644a4a11e08
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 33b8f0215e09dd43c265c7eb8ba08613132fabbc
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870311"
---
# <a name="concurrency-visualizer-sdk"></a>SDK Vizualizéru souběžnosti
Svůj zdrojový kód můžete instrumentovat pomocí sady Vizualizátor souběžnosti SDK pro zobrazení dalších informací v Vizualizátor souběžnosti. Můžete přidružit další data k fázím a událostem ve vašem kódu. Tyto další vizualizace se označují jako *značky*.  Úvodní návod najdete v tématu [představení sady Vizualizátor souběžnosti SDK](http://go.microsoft.com/fwlink/?LinkId=235405).

## <a name="properties"></a>Vlastnosti
 Příznaky, rozsahy a zprávy obsahují dvě vlastnosti: kategorie a důležitost. V dialogovém okně [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) lze pomocí těchto vlastností filtrovat sadu zobrazených značek. Kromě toho tyto vlastnosti ovlivňují vizuální znázornění značek. Například velikost příznaků se používá k reprezentaci důležitosti. Kromě toho se k označení kategorie používá barva.

## <a name="basic-usage"></a>Základní využití
 Vizualizátor souběžnosti zpřístupňuje výchozího zprostředkovatele, který můžete použít ke generování značek. Zprostředkovatel je již zaregistrován společně s Vizualizátor souběžnosti a vy nemusíte nic dalšího dělat, aby se značky v uživatelském rozhraní zobrazovaly.

### <a name="c-and-visual-basic"></a>C# a Visual Basic
 V C#jazyce Visual Basic a jiném spravovaném kódu použijte výchozího poskytovatele voláním metod ve třídě [značek](/previous-versions/hh694099(v=vs.140)) . Zpřístupňuje čtyři metody generování značek: [WriteFlag](/previous-versions/hh694185%28v%3dvs.140%29), [EnterSpan](/previous-versions/hh694205(v=vs.140)), [WriteMessage](/previous-versions/hh694161(v=vs.140))a [WriteAlert](/previous-versions/hh694180(v=vs.140)). Pro tyto funkce existuje více přetížení v závislosti na tom, zda chcete pro vlastnosti použít výchozí hodnoty.  Nejjednodušší přetížení přebírá pouze parametr řetězce, který určuje popis události. Popis se zobrazí v sestavách Vizualizátor souběžnosti.

##### <a name="to-add-sdk-support-to-a-c-or-visual-basic-project"></a>Přidání podpory sady SDK do projektu C# nebo Visual Basic

1. Na panelu nabídek vyberte možnost **analyzovat**, **Vizualizér souběžnosti**, **přidejte sadu SDK do projektu**.

2. Vyberte projekt, ve kterém chcete získat přístup k sadě SDK, a pak klikněte na tlačítko **Přidat sadu SDK do vybraného projektu** .

3. Přidejte do kódu příkaz Imports nebo using.

    ```csharp
    using Microsoft.ConcurrencyVisualizer.Instrumentation;
    ```

    ```VB
    Imports Microsoft.ConcurrencyVisualizer.Instrumentation
    ```

### <a name="c"></a>C++
 V C++, vytvořte objekt [třídy marker_series](../profiling/marker-series-class.md) a použijte jej k volání funkcí.  Třída zpřístupňuje tři funkce pro generování značek, [metodu marker_series:: write_flag](../profiling/marker-series-write-flag-method.md), [metodu marker_series:: write_message](../profiling/marker-series-write-message-method.md)a [metodu marker_series:: write_alert.](../profiling/marker-series-write-alert-method.md) `marker_series`

##### <a name="to-add-sdk-support-to-a-c-or-c-project"></a>Přidání podpory sady SDK do projektu C++ nebo jazyka C

1. Na panelu nabídek vyberte možnost **analyzovat**, **Vizualizér souběžnosti**, **přidejte sadu SDK do projektu**.

2. Vyberte projekt, ve kterém chcete získat přístup k sadě SDK, a pak klikněte na tlačítko **Přidat sadu SDK do vybraného projektu** .

3. Pro C++zadejte `cvmarkersobj.h`. Pro C přidejte `cvmarkers.h`.

4. Přidejte příkaz using do kódu.

    ```cpp
    using namespace Concurrency::diagnostic;
    ```

5. Vytvořte objekt a předejte jej `span` konstruktoru. `marker_series`

    ```C++

    marker_series mySeries;
    span s(mySeries, _T("Span description"));

    ```

## <a name="custom-usage"></a>Vlastní využití
 Pro pokročilé scénáře zpřístupňuje sada SDK Vizualizátor souběžnosti více ovládacích prvků.  K pokročilejším scénářům jsou přidruženy dva hlavní koncepty: poskytovatelé značek a značky. Poskytovatelé značek jsou různí zprostředkovatelé trasování událostí pro Windows (každý má jiný identifikátor GUID). Série značek jsou sériové kanály událostí, které jsou generovány jedním zprostředkovatelem. Můžete je použít k organizování událostí generovaných poskytovatelem značek.

#### <a name="to-use-a-new-marker-provider-in-a-c-or-visual-basic-project"></a>Použití nového poskytovatele značek v Visual Basic projektu C# nebo

1. Vytvořte objekt [MarkerWriter](/previous-versions/hh694138(v=vs.140)) .  Konstruktor přijímá identifikátor GUID.

2. Chcete-li zaregistrovat poskytovatele, otevřete dialogové okno [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) Vizualizátor souběžnosti.  Vyberte kartu **značky** a pak klikněte na tlačítko **Přidat nového poskytovatele** . V dialogovém okně [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) zadejte identifikátor GUID, který se použil k vytvoření poskytovatele a popis poskytovatele.

#### <a name="to-use-a-new-marker-provider-in-a-c-or-c-project"></a>Použití nového poskytovatele značek v projektu C++ nebo C

1. K inicializaci PCV_PROVIDER použijte funkci.`CvInitProvider`  Konstruktor přijímá identifikátor GUID * a PCV_PROVIDER\*.

2. Chcete-li zaregistrovat poskytovatele, otevřete dialogové okno [Upřesnit nastavení](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) .  Vyberte kartu **značky** a pak klikněte na tlačítko **Přidat nového poskytovatele** . V tomto dialogovém okně zadejte identifikátor GUID, který se použil k vytvoření poskytovatele a popis poskytovatele.

#### <a name="to-use-a-marker-series-in-a-c-or-visual-basic-project"></a>Použití řady značek v projektu C# nebo Visual Basic

1. Chcete-li použít novou [MarkerSeries](/previous-versions/hh694127(v=vs.140)), nejprve ji vytvořte pomocí objektu [MarkerWriter](/previous-versions/hh694138(v=vs.140)) a pak vygenerujte události značky přímo z nové řady.

    ```csharp
    MarkerSeries series1 = myMarkerWriter.CreateMarkerSeries("Series 1");
    series1.WriteFlag("My flag");
    ```

    ```VB
    Dim series1 As New myMarkerWriter.CreateMarkerSeries("Series 1")
    series1.WriteFlag("My flag")
    ```

#### <a name="to-use-a-marker-series-in-a-c-project"></a>Použití řady značek v C++ projektu

1. `marker_series` Vytvořte objekt.  Z této nové řady můžete generovat události.

    ```scr
    marker_series series;
    series.write_flag(_T("Hello world!"));
    ```

#### <a name="to-use-a-marker-series-in-a-c-project"></a>Použití řady značek v projektu jazyka C

1. K vytvoření PCV_MARKERSERIES použijte funkci.`CvCreateMarkerSeries`

    ```C++
    PCV_MARKERSERIES series;
    CvCreatemarkerSeries(myProvider, _T("My Series"), &series);
    CvWriteFlag(series, _T("Writing a flag"));
    ```

## <a name="see-also"></a>Viz také:

|Název|Popis|
|-----------|-----------------|
|[C++odkaz na knihovnu](../profiling/cpp-library-reference.md)|Popisuje rozhraní API Vizualizátor souběžnosti pro C++.|
|[Referenční dokumentace knihovny jazyka C](../profiling/c-library-reference.md)|Popisuje rozhraní API Vizualizátor souběžnosti pro jazyk C.|
|[Instrumentace](/previous-versions/hh694104(v=vs.140))|Popisuje rozhraní API Vizualizátor souběžnosti pro spravovaný kód.|
|[Vizualizér souběžnosti](../profiling/concurrency-visualizer.md)|Referenční informace o zobrazeních a sestavách datových souborů profilování, které jsou generovány pomocí metody souběžnosti a které obsahují data spuštění vlákna.|