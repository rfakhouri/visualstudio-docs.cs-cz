---
title: "Výsledky metrik v sadě Visual Studio Code | Microsoft Docs"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c259a1d303c741d4e36af46250073b0378a65f8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-code-metrics-data"></a>Práce s daty metrik kódu

**Výsledky metrik kódu** zobrazují data, která je generován analýza metriky kódu. Další informace o data hodnoty metrik kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

## <a name="displaying-code-metrics-results"></a>Zobrazení výsledků metrik kódu

**Výsledky metrik kódu** okno se zobrazí automaticky při generování výsledků metrik kódu. Kdykoli můžete také zobrazit okno.

### <a name="to-display-the-code-metrics-results-window"></a>Chcete-li zobrazit okno výsledků metrik kódu

- Na **analyzovat** nabídce zvolte **Windows** > **výsledky metrik kódu**.

   \-nebo –

- Na **zobrazení** nabídce zvolte **ostatní okna** > **výsledky metrik kódu**.

   **Výsledky metrik kódu** okno se zobrazí, i v případě, že neobsahuje žádné výsledky.

### <a name="to-view-code-metrics-details"></a>Chcete-li zobrazit podrobnosti metriky kódu

Pokud byly generovány výsledky metrik kódu, rozbalte ve stromu v **hierarchie** sloupce.

## <a name="filtering-code-metrics-results"></a>Filtrování výsledků metriky kódu

Můžete filtrovat výsledky, které se zobrazují v **výsledky metrik kódu** pomocí panelu nástrojů v horní části okna. Například můžete chtít zobrazit pouze s indexem udržovatelnosti nižší než 65 výsledky.

**Filtru** rozevírací seznam obsahuje názvy sloupců výsledky. Pokud filtr je definován, se přidá do dolní části seznamu společně s odsazení. Seznam může obsahovat posledních deset filtry, které byly definovány.

### <a name="to-filter-the-code-metrics-results"></a>Pro filtrování výsledků metriky kódu

1.  Z **filtru** seznamu, vyberte název sloupce.

2.  V **Min**, zadejte minimální hodnotu, který se má zobrazit.

3.  V **maximální**, zadejte maximální hodnotu, který se má zobrazit.

4.  Klikněte **použít filtr** tlačítko.

5.  Pokud chcete zobrazit podrobnosti výsledku, rozbalte stromovou strukturu hierarchie.

## <a name="adding-removing-and-rearranging-data-columns"></a>Přidání, odebrání a změna uspořádání datové sloupce

Můžete přidat nebo odebrat výsledků sloupců z **výsledky metrik kódu** okno. Kromě toho můžete přeuspořádat výsledky sloupců, aby se zobrazily v pořadí, ve kterém chcete.

### <a name="to-remove-a-column"></a>Pokud chcete odebrat sloupec

1. Klikněte **přidat nebo odebrat sloupce** tlačítko.

     \-nebo - klikněte pravým tlačítkem na záhlaví libovolného sloupce a pak klikněte na tlačítko **přidat nebo odebrat sloupce**.

1. V **přidat nebo odebrat sloupce** dialogové okno, zrušte zaškrtnutí políčka pro sloupec, který chcete odebrat a pak klikněte na **OK**.

### <a name="to-add-a-previously-removed-column"></a>Chcete-li přidat sloupec dříve odstraněných

1. Klikněte **přidat nebo odebrat sloupce** tlačítko.

     \-nebo –

     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na **přidat nebo odebrat sloupce**.

1. V **přidat nebo odebrat sloupce** dialogové okno pole, zaškrtněte políčko pro sloupec, který chcete přidat a pak klikněte na tlačítko **OK**.

### <a name="to-rearrange-columns"></a>Chcete-li změnit sloupce

1. Klikněte **přidat nebo odebrat sloupce** tlačítko.

     \-nebo –

     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na **přidat nebo odebrat sloupce**.

1. V **přidat nebo odebrat sloupce** dialogovém okně vyberte sloupec, který chcete přesunout a potom klikněte na šipku nahoru nebo šipku dolů.

1. Pokud sloupec je nastavený, kam chcete, klikněte na tlačítko **OK**.

## <a name="copying-data-to-the-clipboard-or-excel"></a>Kopírování dat do schránky nebo v aplikaci Excel

Můžete vybrat a Kopírovat vybraný řádek dat metrik kódu do schránky jako textový řetězec, který obsahuje jeden řádek pro název a hodnotu pro každý sloupec data. Můžete také kliknout na **otevřete výběr v aplikaci Microsoft Excel** exportovat všechny výsledky metrik kódu do tabulky aplikace Excel.

## <a name="creating-a-work-item-based-on-code-metric-results"></a>Vytvoření pracovní položky na základě výsledků metriky kódu

Můžete vytvořit [Visual Studio Team Services (VSTS)](/vsts/index) pracovní položka, která je založená na výsledkem **výsledků metriky kódu** okno. Když je vytvořena pracovní položka, Visual Studio automaticky zadá název v **název** data metriky pole a kódu v rámci **historie** kartě.

Další informace o služby VSTS pracovní položky, najdete v části [pracovní položky (VSTS)](/vsts/work/work-items/index).

### <a name="to-create-a-work-item-based-on-a-result"></a>K vytvoření pracovní položky podle výsledku

1.  Klikněte pravým tlačítkem na výsledek.

2.  Přejděte na příkaz **vytvoření pracovní položky**a pak klikněte na typ pracovní položky, kterou chcete vytvořit (**chyb**, **úloh**, a tak dále).

3.  Dokončete formulář pracovní položky pomocí vyplnění všech povinných polí.

4.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše** uložit pracovní položku.

### <a name="to-create-a-bug-based-on-a-result"></a>K vytvoření chyby podle výsledku

1.  Klikněte na výsledek a vyberte ji.

2.  Klikněte **vytvoření pracovní položky** tlačítko.

3.  Dokončete formulář pracovní položky pomocí vyplnění všech povinných polí.

4.  Na **soubor** nabídky, klikněte na tlačítko **Uložit vše** uložit pracovní položku.

## <a name="see-also"></a>Viz také

[Hodnoty metrik kódu](../code-quality/code-metrics-values.md)  
[Postupy: Vygenerování dat metrik kódu](../code-quality/how-to-generate-code-metrics-data.md)