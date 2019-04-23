---
title: 'Postupy: Naplnění listů daty z databáze'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets [Office development in Visual Studio], populating
- databases [Office development in Visual Studio], populating worksheets
- data [Office development in Visual Studio], adding to worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 67c12843d00bf8d5af51fa7af3175077527afa58
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079137"
---
# <a name="how-to-populate-worksheets-with-data-from-a-database"></a>Postupy: Naplnění listů daty z databáze

Stejným způsobem, že přistupujete k datům v projektech Windows Forms, můžou k datům v projektech Office úrovni dokumentu. Použít stejné nástroje a kódu přenést data do vašeho řešení a ovládací prvky Windows Forms můžete použít i pro zobrazení údajů. Kromě toho můžete využít výhod ovládací prvky hostitelské ovládací prvky, které jsou nativních objektů v aplikaci Microsoft Office Excel, které je vylepšené o události a datové vazby funkce volána. Další informace najdete v tématu [hostovat položky a hostujte Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).

[!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

Následující příklad ukazuje, jak přidat ovládací prvky vázané na data v projekty na úrovni dokumentu pomocí návrháře. Příklad toho, jak přidat ovládací prvky vázané na data v projektech na úrovni aplikace za běhu, naleznete v tématu [názorný postup: Rozšířené datové vazby v projektu doplňku VSTO](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md).

![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Přenos dat do listu aplikace Excel? ](http://go.microsoft.com/fwlink/?LinkID=130277), a [postup: Využití dat z databáze v aplikaci Excel? ](http://go.microsoft.com/fwlink/?LinkID=130287).

## <a name="add-a-data-bound-control-to-a-worksheet-at-design-time"></a>Přidejte ovládací prvek vázaný na data na list v době návrhu

### <a name="to-populate-a-worksheet-with-data-from-a-database"></a>K naplnění listů daty z databáze

1. Otevřete úrovni dokumentu projektu aplikace Excel v sadě Visual Studio, otevřete sešit v návrháři.

2. Otevřít **zdroje dat** okna a vytvořte zdroj dat pro váš projekt. Další informace najdete v tématu [přidat nové připojení](../data-tools/add-new-connections.md).

3. Přetáhněte pole nebo tabulku, kterou z **zdroje dat** okno do listu.

Jeden z následujících ovládacích prvků je vytvořena na listu:

- Pokud přetáhnete pole, <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je vytvořen v listu. Další informace najdete v tématu [namedrange – ovládací prvek](../vsto/namedrange-control.md).

- Pokud přetáhnete tabulky <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek je vytvořen v listu. Další informace najdete v tématu [ListObject – ovládací prvek](../vsto/listobject-control.md).

Můžete přidat jiného ovládacího prvku tak, že vyberete v tabulce nebo pole **zdroje dat** okno a následným výběrem jiného ovládacího prvku z rozevíracího seznamu.

## <a name="objects-in-the-project"></a>Objekty v projektu

Kromě ovládacího prvku jsou následující objekty související s daty automaticky přidány do projektu:

- Typové datové sady, který zapouzdřuje tabulek dat, které jste se připojili v databázi. Další informace najdete v tématu [datovou sadu nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

- A <xref:System.Windows.Forms.BindingSource> ovládacího prvku, která se připojuje k typové datové sady. Další informace najdete v tématu [přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview).

- TableAdapter, který se připojuje k databázi typové datové sady. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

- TableAdapterManager, který se používá ke koordinaci adaptéry tabulek v datové sadě, aby povolovala hierarchické aktualizace. Další informace najdete v tématu [hierarchické aktualizace](../data-tools/hierarchical-update.md) a [TableAdapterManager odkaz](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference).

Při spuštění projektu ovládací prvek zobrazí první záznam ve zdroji dat. Můžete použít <xref:System.Windows.Forms.BindingSource> umožňující uživatelům procházet záznamy.

### <a name="to-scroll-through-the-records"></a>Procházet záznamy

- Použití <xref:System.Windows.Forms.BindingSource> metody jako <xref:System.Windows.Forms.BindingSource.MoveNext%2A> a <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>.

Informace o tom, jak odesílat aktualizace do typové datové sady a databáze najdete v tématu [jak: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Přidání nových zdrojů dat](../data-tools/add-new-data-sources.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Postupy: Naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Postupy: Naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Postupy: Naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)
- [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Postup: Přenos dat do Excelového listu](http://go.microsoft.com/fwlink/?LinkID=130277)
- [Postup: Využití dat z databáze v aplikaci Excel?](http://go.microsoft.com/fwlink/?LinkID=130287)