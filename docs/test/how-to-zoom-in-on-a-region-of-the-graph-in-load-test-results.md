---
title: "Přiblížení grafy výsledků testu zatížení v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
f1_keywords:
- vs.test.load.monitor.graphzoom
helpviewer_keywords:
- graphs, analyzing load tests
- load tests, zooming with graphs
ms.assetid: 729b4c30-4bc3-4698-91b3-17a676897443
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: d5b65107655d27da5ace994ac56fc989fc83004c
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results"></a>Postupy: Přiblížení oblasti grafu ve výsledcích zátěžového testu

Po dokončení testu zatížení můžete přiblížení řádky přiblížení a přejděte do oblasti grafu. Pomocí zvětšení, můžete zkontrolovat data, která byla vygenerována během zátěžového testu spusťte jemnějšího podrobně.

> [!NOTE]
> Zvětšení v je k dispozici pouze při analýze výsledek dokončeného zátěžového testu, není, když se sledování výsledků testu spuštěné.

 Ovládací prvek Lupa je viditelná pouze v analyzátor načíst otestovat, při zobrazení výsledků testů zatížení v režimu změna měřítka zobrazení. Změna měřítka zobrazení režimu je vytvořeno v zobrazení grafu při zátěžový test byla dokončena nebo je načtena zátěžový test, která byla dříve spuštěna. Můžete zobrazit nebo skrýt přiblížení ovládacích prvků na v grafech pomocí Zobrazit zvětšení ovládacích prvků na panelu nástrojů.

 Přiblížení vodorovné osy x lze upravit k analýze konkrétní časová období, během zátěžového testu. Přiblížení svislé osy y lze upravit k analýze rozsahy konkrétní hodnotu čítače, které jsou zahrnuty v grafu.

 Vodorovné osy a ovládací prvky zvětšení rozsah svislé hodnotu lze upravit pomocí myši. Řízení vodorovné osy může být také upravena pomocí klávesy šipka doleva a doprava. Pomocí klávesy se šipkami upravte ovládacího prvku přiblížení, můžete upravit rozsah windows interval vzorkování 1 najednou. Pomocí klávesy SHIFT a šipku provádí úpravy 10 intervalů vzorkování.

 Upravit ovládací prvek Lupa pomocí klávesy šipka, nejdřív nastavte fokus na ovládací prvek Lupa pomocí klávesy TAB. Když levý jezdec fokus, klávesy se šipkami přesune počáteční hranice okna přiblížení 1 interval doleva nebo doprava. Pokud je fokus nastavený na posuvníku možnost center, můžete posouvat přiblížení okno doleva nebo doprava 1 interval vzorkování bez nutnosti změny velikosti okna přiblížení klávesy se šipkami. A nakonec pravé straně posuvníku přesune, rozšíření nebo snížením rozsahu konce okno přiblížení o 1 interval vzorkování.

 Pokud chcete vrátit ovládací prvky vodorovného a svislého přiblížení zobrazíte úplné časového harmonogramu a hodnota rozsahy, můžete použít **zvětšení limitu vodorovné** možnost, **zvětšení limitu svislé** možnost, nebo **Oddálit Obě** možnost v rozbalovací nabídce v grafu.

> [!TIP]
> Můžete použít **synchronizovat vodorovné zvětšení ovládací prvky** na panelu nástrojů. Chcete-li zapnout nebo vypnout automatické vodorovné přiblížení synchronizace. V synchronizaci na všechny přibližování týkají grafu se také být použit na všechny ostatní grafy v zobrazení grafů.

 ![Graf ovládání pro zvětšení zobrazení](../test/media/ltest_zoomcontrol.png "LTest_ZoomControl") ovládací prvek Lupa grafu

 Na předchozím obrázku má byla systému za testovací grafu přiblížení můžete prozkoumat problémy prahovou hodnotu. Byly povoleny překročení mezních hodnot s použitím **zobrazit porušení prahové hodnoty v grafu** z **možnosti grafu** rozevírací seznam v panelu nástrojů.

 Další informace najdete v tématu [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="displaying-graphs"></a>Zobrazení grafů
 Než změníte zobrazení grafu zvětšování nebo zmenšování nebo posouvání, pomocí následujícího postupu zobrazit grafy.

### <a name="to-display-graphs"></a>Chcete-li zobrazit grafy

1.  Spusťte zátěžový test, dokud se nedokončí.

2.  Na konci zátěžového testu, spuštění, zvolte **Ano** v dialogovém okně s dotazem, o zobrazení výsledků z výsledků zátěžových testů úložiště.

     \- nebo –

     Zobrazte podrobnosti o dříve spuštěném zátěžovém testu. Další informace najdete v tématu [postupy: přístup výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md).

3.  Zvolte **grafy** Pokud vaše grafy se nezobrazují.

4.  Pokud se nezobrazují přiblížení řádky, zvolte **Zobrazit zvětšení ovládací prvky**.

     Dva řádky přiblížení jsou k dispozici pro každého grafu. Panel přiblížení, který určuje svislé měřítko se zobrazí vlevo od grafu. Na panelu přiblížení, kterými se řídí vodorovné škálování se zobrazí v grafu.

     Každý panel přiblížení má dvě obslužné rutiny. Popisovač je obdélníkovou oblast na obou koncích panelu přiblížení.

## <a name="zooming-and-scrolling"></a>Přibližování a posouvání
 Pokud máte více grafů, které se zobrazí, můžete zachovat jejich shoda tak, aby se zobrazovala stejnou část zátěžový test, spustit.

### <a name="to-synchronize-zooming-and-scrolling"></a>K synchronizaci přibližování a posouvání

1.  V Analyzéru zátěžového testu zvolte **synchronizovat vodorovné zvětšení ovládací prvky**.

     Pokud je vybraná tlačítko Synchronizovat vodorovné zvětšení ovládací prvky, přibližování a posouvání ose grafu jednotlivých také zvětší a posune ose jiných grafů.

2.  Vyberte znovu synchronizovat vodorovné zvětšení ovládací prvky.

     Pokud není vybrané tlačítko Synchronizovat vodorovné zvětšení ovládací prvky, přibližování a posouvání ose grafu jednotlivých ovlivňuje pouze tohoto grafu.

### <a name="to-zoom-and-scroll-to-a-region-of-the-graph"></a>Přiblížení a přejděte do oblasti grafu

1.  Na panelu přiblížení pod graf přetažením úchytu levé straně vpravo.

     To zvětší pozdější součástí testovacím běhu. Podobně přetažením úchytu pravé straně vlevo zvětší dřívější části spuštění testu.

2.  Chcete-li zvětšit určitou oblast, posuňte obou popisovače do středu graf.

     Čím bližší dvě obslužné rutiny jsou na každý jiný více přiblížit zobrazíte kratší, jemnějšího segmenty zátěžový test.

     Zvolte části center panelu přiblížení a poté ji přetáhněte do přejděte na určité místo v zátěžovém testu.

### <a name="to-zoom-to-a-region-of-the-graph-by-choosing-and-dragging"></a>Pro výběr a přetažením přiblížení oblasti grafu

1.  Vyberte graf, který na jednom konci oblasti přiblížení.

2.  Přetáhněte ukazatel myši na druhém konci oblasti přiblížení.

3.  Uvolnění tlačítka myši.

     To zvětší k oblasti, která jste definovali výběr a přetažením.

 Následující postup popisuje, jak rychle zvětšit bez nutnosti upravit konců panelu přiblížení.

### <a name="to-zoom-out"></a>Chcete-li oddálení

1.  Klikněte pravým tlačítkem na možnosti v grafu.

2.  V místní nabídce vyberte **zvětšení limitu vodorovné**.

     Tím se zmenší zobrazíte spuštění celou dobu trvání zátěžový test.

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Přidání a odstranění čítačů pro grafy](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)