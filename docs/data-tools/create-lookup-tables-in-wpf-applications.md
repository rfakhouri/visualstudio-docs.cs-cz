---
title: Vytváření vyhledávacích tabulek v aplikacích WPF
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
ms.assetid: 56a1fbff-c7e8-4187-a1c1-ffd17024bc1b
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fe90d81c2fa6f06bdf29adc6ab223c58b8440daa
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="create-lookup-tables-in-wpf-applications"></a>Vytváření vyhledávacích tabulek v aplikacích WPF
Termín *vyhledávací tabulky* (někdy nazývané *vyhledávání vazby*) popisuje ovládacího prvku, který zobrazí informace z tabulky jeden datový na základě hodnoty pole cizího klíče v druhé tabulce. Můžete vytvořit vyhledávací tabulku tak, že přetáhnete hlavní uzel nadřazené tabulky nebo objekt v **zdroje dat** oken na ovládací prvek, který je již vázána na sloupec nebo vlastnost v související podřízené tabulce.

Předpokládejme například tabulku `Orders` v prodejní databázi. Každý záznam v `Orders` tabulka obsahuje `CustomerID` určující, které zákazníka umístit pořadí. `CustomerID` Je cizí klíč, který odkazuje na záznam zákazníka v `Customers` tabulky. Při zobrazení seznamu objednávky z `Orders` tabulky, můžete zobrazovaný název skutečnou zákazníků místo `CustomerID`. Protože jméno zákazníka `Customers` tabulky, budete muset vytvořit vyhledávací tabulku pro zobrazení jméno zákazníka. Používá tabulky vyhledávání `CustomerID` hodnotu `Orders` záznam přejděte relace a vrátí jméno zákazníka.

## <a name="to-create-a-lookup-table"></a>K vytvoření vyhledávací tabulky

1.  Do projektu přidejte jeden z následujících typů zdrojů dat s souvisejících dat:

    -   Datové sady nebo datového modelu Entity.

    -   Služby WCF Data Service, služby WCF nebo webové službě. Další informace najdete v tématu [postupy: připojení k datům ve službě](../data-tools/how-to-connect-to-data-in-a-service.md).

    -   Objekty. Další informace najdete v tématu [vazby na objekty v sadě Visual Studio](bind-objects-in-visual-studio.md).

    > [!NOTE]
    >  Před vytvořením vyhledávací tabulky, musí existovat dva související tabulky nebo objekty jako zdroj dat pro projekt.

2.  Otevřete **WPF Designer**a ujistěte se, že návrháře obsahuje kontejner, který je cíle platný přetažení u položek v **zdroje dat** okno.

     Další informace o cílů přemístění platná najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

3.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat** otevřete **zdroje dat** okno.

4.  Rozbalte uzly v **zdroje dat** okno, dokud se nezobrazí v nadřazené tabulce nebo objekt a související podřízenou tabulku nebo objekt.

    > [!NOTE]
    >  Související podřízenou tabulku nebo objekt je uzlu, který se zobrazí jako rozšíření podřízený uzel v rámci nadřazené tabulky či objektu.

5.  Klikněte na rozevírací nabídku pro podřízený uzel a vyberte **podrobnosti**.

6.  Rozbalte podřízený uzel.

7.  V části podřízený uzel klikněte na rozevírací nabídky pro položku, která má vztah podřízenými a nadřazenými data. (V předchozím příkladu je to **CustomerID** uzlu.) Vyberte jednu z následujících typů ovládacích prvků, které podporují vazby vyhledávání:

    -   **ComboBox**

    -   **ListBox**

    -   **ListView**

        > [!NOTE]
        >  Pokud **ListBox** nebo **ListView** řízení nejsou uvedené v seznamu, tyto ovládací prvky můžete přidat do seznamu. Informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

    -   Vlastní ovládací prvek, který je odvozen od <xref:System.Windows.Controls.Primitives.Selector>.

        > [!NOTE]
        >  Pro informace o tom, jak přidat vlastní ovládací prvky do seznamu ovládacích prvků můžete vybrat pro položky v **zdroje dat** okně najdete v části [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

8.  Přetáhněte podřízený uzel z **zdroje dat** okna do kontejneru v Návrháři WPF. (V předchozím příkladu je podřízený uzel **objednávky** uzlu.)

     Visual Studio generuje XAML, který vytváří nové ovládací prvky vázané na data pro jednotlivé položky, které přetažení. XAML také přidá nový <xref:System.Windows.Data.CollectionViewSource> pro podřízenou tabulku nebo objekt, který má prostředky cíle přetažení. Pro některé zdroje dat Visual Studio také generuje kód pro načtení dat do tabulky nebo objektu. Další informace najdete v tématu [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

9. Přetáhněte nadřazený uzel z **zdroje dat** oken na ovládací prvek vazby vyhledávání, který jste vytvořili dříve. (V předchozím příkladu nadřazený uzel se **zákazníci** uzlu).

     Visual Studio nastaví některé vlastnosti ovládacího prvku ke konfiguraci vazby pro vyhledávání. Následující tabulka uvádí vlastnosti, které upraví Visual Studio. Pokud potřeby můžete změnit tyto vlastnosti v XAML nebo v **vlastnosti** okno.

    |Vlastnost|Vysvětlivky k nastavení|
    |--------------|----------------------------|
    |<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>|Tato vlastnost určuje kolekci nebo vazby, která se použije k získání dat, která se zobrazí v ovládacím prvku. Visual Studio tato vlastnost nastaví na <xref:System.Windows.Data.CollectionViewSource> pro nadřazené data jste přetáhli do ovládacího prvku.|
    |<xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>|Tato vlastnost určuje cestu položky dat, který se zobrazí v ovládacím prvku. Visual Studio tato vlastnost nastaví na první sloupec nebo vlastnost v nadřazené data po primární klíč, který má datový typ řetězec.<br /><br /> Pokud chcete zobrazit v nadřazené dat na jiný sloupec nebo vlastnost, změňte tuto vlastnost na cestu k jiné vlastnosti.|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>|Visual Studio vytvoří vazbu tato vlastnost sloupec nebo vlastnost podřízené dat, která jste přetáhli do návrháře. Toto je cizí klíč k datům nadřazené.|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValuePath%2A>|Visual Studio tato vlastnost nastaví na cestě sloupce nebo vlastnosti podřízených dat, která je cizí klíč k datům nadřazené.|

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Zobrazení souvisejících dat v aplikaci WPF](../data-tools/display-related-data-in-wpf-applications.md)
- [Návod: Zobrazování souvisejících dat v aplikaci WPF](../data-tools/display-related-data-in-wpf-applications.md)