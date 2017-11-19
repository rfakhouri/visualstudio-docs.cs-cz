---
title: "Práce s daty metrik kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
ms.assetid: 988193ec-b4a3-4e11-b5a1-7334979807d5
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39d45f5d43819dc418b6378d34a19e6af1d8ee12
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-code-metrics-data"></a>Práce s daty metrik kódu
**Výsledky metrik kódu** zobrazují data, která je generován analýza metriky kódu. Další informace o data hodnoty metrik kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).  
  
 Toto téma obsahuje následující oddíly:  
  
-   [Okno výsledků metrik kódu](../code-quality/working-with-code-metrics-data.md#BKMK_CodeMetricsResultsWindow)  
  
-   [Zobrazení výsledků metrik kódu](../code-quality/working-with-code-metrics-data.md#BKMK_DisplayingCodeMetricsResults)  
  
-   [Filtrování výsledků metriky kódu](../code-quality/working-with-code-metrics-data.md#BKMK_FilteringCodeMetricsResults)  
  
-   [Přidání, odebrání a změna uspořádání datové sloupce](../code-quality/working-with-code-metrics-data.md#BKMK_AddingRemovingandRearrangingDataColumns)  
  
-   [Kopírování dat do schránky nebo v aplikaci Excel](../code-quality/working-with-code-metrics-data.md#BKMK_Copying_Data_to_the_Clipboard_or_Excel)  
  
-   [Vytvoření pracovní položky na základě výsledků metriky kódu](../code-quality/working-with-code-metrics-data.md#BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results)  
  
##  <a name="BKMK_CodeMetricsResultsWindow"></a>Okno výsledků metrik kódu  
 **Výsledky metrik kódu** okna mají panelu nástrojů v horní a sloupce, které chcete zobrazit počítané výsledky.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Hierarchie**|**Hierarchie** sloupec obsahuje zobrazení stromu hierarchie kódu, které můžete rozbalit nebo sbalit úroveň podrobností, které chcete zobrazit. Zbývající sloupce Zobrazit počítané výsledky. Můžete skrýt nebo tak, jak chcete uspořádat sloupce s výsledky.|  
|**Udržovatelnost**|**Udržovatelnosti** sloupec obsahuje ikonu, kromě číselné výsledek. Zelená ikona označuje relativně vysoký stupeň udržovatelnosti. Žlutá ikona označuje střední stupeň udržovatelnosti. Červená ikona Určuje nízkou udržovatelnosti a potenciální potíže místo. Tyto indikátory barva odpovídají kategorií závažnosti, které jsou používány pravidlo FxCop AvoidUnmaintainableCode. Toto pravidlo aktivuje chybu, pokud je menší než 10, upozornění, pokud je index mezi 10 a 20 a chybu ani upozornění, pokud index je vyšší než 20 udržovatelnosti index. Index udržovatelnosti je shrnutí tři metriky: cyclomatic složitost řádků kódu a výpočetní složitost. Jeho hodnoty nejsou vyjádřené v jednotkách.|  
  
##  <a name="BKMK_DisplayingCodeMetricsResults"></a>Zobrazení výsledků metrik kódu  
 Při generování výsledků metrik kódu, zobrazí se okno výsledků metrik kódu automaticky. Kdykoli můžete také zobrazit okno.  
  
#### <a name="to-display-the-code-metrics-results-window"></a>Chcete-li zobrazit okno výsledků metrik kódu  
  
-   Na **analyzovat** nabídky, klikněte na tlačítko **Windows** a pak klikněte na **výsledky metrik kódu**.  
  
     \-nebo –  
  
-   Na **zobrazení** nabídky, přejděte na příkaz **ostatní okna** a pak klikněte na **výsledky metrik kódu**.  
  
     I v případě, že neobsahuje žádné výsledky, zobrazí se okno výsledků metrik kódu.  
  
#### <a name="to-view-code-metrics-details"></a>Chcete-li zobrazit podrobnosti metriky kódu  
  
-   Pokud byly generovány výsledky metrik kódu, rozbalte ve stromu v **hierarchie** sloupce.  
  
##  <a name="BKMK_FilteringCodeMetricsResults"></a>Filtrování výsledků metriky kódu  
 Můžete filtrovat výsledky, které se zobrazují v **výsledky metrik kódu** pomocí panelu nástrojů v horní části okna. Například můžete chtít zobrazit pouze s indexem udržovatelnosti nižší než 65 výsledky.  
  
 **Filtru** rozevírací seznam obsahuje názvy sloupců výsledky. Pokud filtr je definován, se přidá do dolní části seznamu společně s odsazení. Seznam může obsahovat posledních deset filtry, které byly definovány.  
  
#### <a name="to-filter-the-code-metrics-results"></a>Pro filtrování výsledků metriky kódu  
  
1.  Z **filtru** seznamu, vyberte název sloupce.  
  
2.  V **Min**, zadejte minimální hodnotu, který se má zobrazit.  
  
3.  V **maximální**, zadejte maximální hodnotu, který se má zobrazit.  
  
4.  Klikněte **použít filtr** tlačítko.  
  
5.  Pokud chcete zobrazit podrobnosti výsledku, rozbalte stromovou strukturu hierarchie.  
  
##  <a name="BKMK_AddingRemovingandRearrangingDataColumns"></a>Přidání, odebrání a změna uspořádání datové sloupce  
 Můžete přidat nebo odebrat výsledků sloupců z **výsledky metrik kódu** okno. Kromě toho můžete přeuspořádat výsledky sloupců, aby se zobrazily v pořadí, ve kterém chcete.  
  
#### <a name="to-remove-a-column"></a>Pokud chcete odebrat sloupec  
  
1.  Klikněte **přidat nebo odebrat sloupce** tlačítko.  
  
     \-nebo –  
  
     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na **přidat nebo odebrat sloupce**.  
  
2.  V **přidat nebo odebrat sloupce** dialogové okno, zrušte zaškrtnutí políčka pro sloupec, který chcete odebrat a pak klikněte na **OK**.  
  
#### <a name="to-add-a-previously-removed-column"></a>Chcete-li přidat sloupec dříve odstraněných  
  
1.  Klikněte **přidat nebo odebrat sloupce** tlačítko.  
  
     \-nebo –  
  
     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na **přidat nebo odebrat sloupce**.  
  
2.  V **přidat nebo odebrat sloupce** dialogové okno pole, zaškrtněte políčko pro sloupec, který chcete přidat a pak klikněte na tlačítko **OK**.  
  
#### <a name="to-rearrange-columns"></a>Chcete-li změnit sloupce  
  
1.  Klikněte **přidat nebo odebrat sloupce** tlačítko.  
  
     \-nebo –  
  
     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na **přidat nebo odebrat sloupce**.  
  
2.  V **přidat nebo odebrat sloupce** dialogovém okně vyberte sloupec, který chcete přesunout a potom klikněte na šipku nahoru nebo šipku dolů.  
  
3.  Pokud sloupec je nastavený, kam chcete, klikněte na tlačítko **OK**.  
  
##  <a name="BKMK_Copying_Data_to_the_Clipboard_or_Excel"></a>Kopírování dat do schránky nebo v aplikaci Excel  
 Můžete vybrat a Kopírovat vybraný řádek dat metrik kódu do schránky jako textový řetězec, který obsahuje jeden řádek pro název a hodnotu pro každý sloupec data. Můžete také kliknout na **Otevřít seznam v aplikaci Microsoft Excel** exportovat všechny výsledky metrik kódu do tabulky aplikace Excel  
  
##  <a name="BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results"></a>Vytvoření pracovní položky na základě výsledků metriky kódu  
 Můžete vytvořit [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] pracovní položka, která je založená na výsledkem **výsledků metriky kódu** okno. Když je vytvořena pracovní položka, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky zadá název v **název** data metriky pole a kódu v rámci **historie** kartě.  
  
 Další informace o tom, jak vytvářet pracovní položky, naleznete v části [vytvořit pracovní položku &#91; přesměrováno &#93;](http://msdn.microsoft.com/en-us/24b2e064-16ac-4bf0-8de4-98a1f48b8c4b).  
  
#### <a name="to-create-a-work-item-based-on-a-result"></a>K vytvoření pracovní položky podle výsledku  
  
1.  Klikněte pravým tlačítkem na výsledek.  
  
2.  Přejděte na příkaz **vytvoření pracovní položky**a pak klikněte na typ pracovní položky, kterou chcete vytvořit (**chyb**, **úloh**, a tak dále).  
  
3.  Dokončete formulář pracovní položky pomocí vyplnění všech povinných polí.  
  
4.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše** uložit pracovní položku.  
  
#### <a name="to-create-a-bug-based-on-a-result"></a>K vytvoření chyby podle výsledku  
  
1.  Klikněte na výsledek a vyberte ji.  
  
2.  Klikněte **vytvoření pracovní položky** tlačítko.  
  
3.  Dokončete formulář pracovní položky pomocí vyplnění všech povinných polí.  
  
4.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše** uložit pracovní položku.  
  
## <a name="see-also"></a>Viz také  
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)   
 [Postupy: vygenerování dat metrik kódu](../code-quality/how-to-generate-code-metrics-data.md)