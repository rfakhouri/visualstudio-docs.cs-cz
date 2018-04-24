---
title: Zobrazení souvisejících dat v aplikaci WPF
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 3aa80194-0191-474d-9d28-5ec05654b426
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b293656a0eeffeba304ef4692f9c021ae9639d22
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="display-related-data-in-wpf-applications"></a>Zobrazení souvisejících dat v aplikaci WPF
V některých aplikacích můžete chtít pracovat s daty, která pochází z více tabulek nebo entity, které se vztahují k sobě navzájem v relaci nadřazený podřízený. Například můžete chtít zobrazit tabulku, která zobrazuje zákazníky z `Customers` tabulky. Když uživatel vybere konkrétního zákazníka, jiné mřížky zobrazí objednávky tohoto zákazníka ze související `Orders` tabulky.

Můžete vytvořit ovládací prvky vázané na data, která zobrazení souvisejících dat tak, že přetáhnete položky z **zdroje dat** okna Návrháře WPF.

## <a name="to-create-controls-that-display-related-records"></a>Chcete-li vytvořit ovládací prvky, které zobrazují související záznamy

1. Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat** otevřete **zdroje dat** okno.

2. Klikněte na tlačítko **přidat nový zdroj dat**a dokončete **konfigurace zdroje dat** průvodce.

3. Otevřete návrháře WPF a ujistěte se, že návrháře obsahuje kontejner, který je cílem platný drop pro položky v **zdroje dat** okno.

     Další informace o cílů přemístění platná najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

4. V **zdroje dat** časové období, rozbalte uzel, který představuje v nadřazené tabulce, nebo objekt v relaci. Nadřazené tabulky nebo objekt je na straně "1" vztah jeden mnoho.

5. Přetáhněte nadřazený uzel (nebo všechny jednotlivé položky nadřazený uzel) z **zdroje dat** okna do cíle přetažení platný v návrháři.

     Visual Studio generuje XAML, který vytváří nové ovládací prvky vázané na data pro každou položku, která přetažení. XAML také přidá nový <xref:System.Windows.Data.CollectionViewSource> pro nadřazenou tabulku nebo objekt, který má prostředky cíle přetažení. Pro některé zdroje dat Visual Studio také generuje kód chcete načíst data do nadřazené tabulky či objektu. Další informace najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6. V **zdroje dat** okně vyhledejte související podřízenou tabulku nebo objekt. Související podřízené tabulky a objekty se zobrazí jako rozšíření uzly v dolní části seznamu nadřazeného uzlu data.

7. Přetáhněte podřízený uzel (nebo všechny jednotlivé položky podřízený uzel) z **zdroje dat** okna do cíle přetažení platný v návrháři.

     Visual Studio generuje XAML, který vytváří nové ovládací prvky vázané na data pro jednotlivé položky, které přetažení. XAML také přidá nový <xref:System.Windows.Data.CollectionViewSource> pro podřízenou tabulku nebo objekt, který má prostředky cíle přetažení. Tento nový <xref:System.Windows.Data.CollectionViewSource> je vázána na vlastnost nadřazené tabulky nebo objekt, který jste právě přetáhli návrháře. Pro některé zdroje dat Visual Studio také generuje kód chcete načíst data do podřízenou tabulku či objekt.

     Následující obrázek ukazuje související **objednávky** tabulky **zákazníci** tabulky v datové sadě v **zdroje dat** okno.

     ![Okno zdroje dat, zobrazující vztah](../data-tools/media/datasources2.gif "DataSources2")

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Vytváření vyhledávacích tabulek v aplikacích WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)