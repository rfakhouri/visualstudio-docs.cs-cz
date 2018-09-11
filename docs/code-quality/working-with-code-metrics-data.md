---
title: Okno výsledků metrik kódu v sadě Visual Studio
ms.date: 12/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40e265e5bdc453ec658de16f288e9c184979975f
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44321252"
---
# <a name="using-the-code-metrics-results-window"></a>Pomocí okna výsledků metrik kódu

**Výsledků metrik kódu** okně se zobrazí data, která je vygenerován nástrojem analýza kódu metriky. Další informace o hodnoty dat metrik kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

## <a name="displaying-code-metrics-results"></a>Zobrazení výsledků metrik kódu

**Výsledků metrik kódu** okno se automaticky zobrazí při generování výsledků metrik kódu. Kdykoli můžete také zobrazit okna.

### <a name="to-display-the-code-metrics-results-window"></a>Chcete-li zobrazit okno výsledků metrik kódu

- Na **analyzovat** nabídce zvolte **Windows** > **výsledků metrik kódu**.

   \- nebo –

- Na **zobrazení** nabídce zvolte **ostatní Windows** > **výsledků metrik kódu**.

**Výsledků metrik kódu** se zobrazí okno, i v případě, že neobsahuje žádné výsledky.

### <a name="to-view-code-metrics-details"></a>Chcete-li zobrazit podrobnosti metrik kódu

Pokud byly vytvořeny výsledky metrik kódu, rozbalte ve stromu v **hierarchie** sloupce.

## <a name="filtering-code-metrics-results"></a>Filtrování výsledků metrik kódu

Můžete filtrovat výsledky, které jsou zobrazeny v **výsledků metrik kódu** pomocí panelu nástrojů v horní části okna. Například můžete chtít zobrazit pouze výsledky, které mají index udržovatelnosti pod 65.

**Filtr** rozevírací seznam obsahuje názvy sloupců výsledky. Když je definována filtr, přidá se do dolní části seznamu spolu s odsazení. Seznam může obsahovat posledních deset filtry, které byly definovány.

### <a name="to-filter-the-code-metrics-results"></a>K filtrování výsledků metrik kódu

1.  Z **filtr** seznamu, vyberte název sloupce.

2.  V **Min**, zadejte minimální hodnotu, který se má zobrazit.

3.  V **maximální**, zadejte maximální hodnotu, který se má zobrazit.

4.  Klikněte na tlačítko **použít filtr** tlačítko.

5.  Pokud chcete zobrazit podrobnosti výsledku, rozbalte stromovou strukturu hierarchie.

## <a name="adding-removing-and-rearranging-data-columns"></a>Přidání, odebrání a změna uspořádání dat sloupců

Můžete přidat nebo odebrat výsledky ze sloupce **výsledků metrik kódu** okna. Kromě toho můžete změnit uspořádání sloupců výsledky tak, aby byly zobrazeny v pořadí, ve kterém chcete.

### <a name="to-remove-a-column"></a>Pokud chcete odebrat sloupec

1. Klikněte na tlačítko **Přidat/odebrat sloupce** tlačítko.

     \- nebo klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na tlačítko **Přidat/odebrat sloupce**.

1. V **Přidat/odebrat sloupce** dialogové okno, zrušte zaškrtnutí políčka pro sloupce, které chcete odebrat a pak klikněte na tlačítko **OK**.

### <a name="to-add-a-previously-removed-column"></a>Chcete-li přidat dříve odebrané sloupce

1. Klikněte na tlačítko **Přidat/odebrat sloupce** tlačítko.

     \- nebo –

     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na tlačítko **Přidat/odebrat sloupce**.

1. V **Přidat/odebrat sloupce** dialogového okna, vyberte zaškrtávací políčko pro sloupec, který chcete přidat a potom klikněte na tlačítko **OK**.

### <a name="to-rearrange-columns"></a>Chcete-li změnit uspořádání sloupců

1. Klikněte na tlačítko **Přidat/odebrat sloupce** tlačítko.

     \- nebo –

     Klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na tlačítko **Přidat/odebrat sloupce**.

1. V **Přidat/odebrat sloupce** dialogového okna, vyberte sloupec, který chcete přesunout a potom klikněte na šipku nahoru nebo šipku dolů.

1. Když sloupec je umístěn, kam chcete, klikněte na tlačítko **OK**.

## <a name="copying-data-to-the-clipboard-or-excel"></a>Kopírování dat do schránky nebo aplikace Excel

Můžete vybrat a kopírovat vybraného řádku dat metrik kódu do schránky jako textový řetězec, který obsahuje jeden řádek pro název a hodnotu každého sloupce data. Můžete také kliknout na **otevřít výběr v aplikaci Microsoft Excel** exportovat všechny výsledky metrik kódu do Excelové tabulky.

## <a name="creating-a-work-item-based-on-code-metric-results"></a>Vytváření pracovních položek na základě výsledků metrik kódu

Můžete vytvořit [panely Azure](/azure/devops/boards/index?view=vsts) výsledkem pracovní položku, která je založena na **výsledků metrik kódu** okna. Po vytvoření pracovní položky sady Visual Studio automaticky zadá název **název** pole a kód dat metrik v části **historie** kartu.

Další informace o Azure panelů pracovní položky, naleznete v tématu [pracovní položky](/azure/devops/boards/work-items/index?view=vsts).

### <a name="to-create-a-work-item-based-on-a-result"></a>Chcete-li vytvořit pracovní položku podle výsledku

1.  Klikněte pravým tlačítkem na výsledek.

2.  Přejděte na **vytvořit pracovní položku**a potom klikněte na typ pracovní položky, kterou chcete vytvořit (**chyb**, **úloh**a tak dále).

3.  Vyplňte formulář pracovní položky vyplnění všech povinných polích.

4.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše** k uložení pracovní položky.

### <a name="to-create-a-bug-based-on-a-result"></a>Vytvořit chybu na základě výsledku

1.  Klikněte na výsledek a vyberte ji.

2.  Klikněte na tlačítko **vytvořit pracovní položku** tlačítko.

3.  Vyplňte formulář pracovní položky vyplnění všech povinných polích.

4.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše** k uložení pracovní položky.

## <a name="see-also"></a>Viz také:

- [Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
- [Postupy: vygenerování dat metrik kódu](../code-quality/how-to-generate-code-metrics-data.md)