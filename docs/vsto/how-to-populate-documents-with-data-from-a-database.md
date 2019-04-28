---
title: 'Postupy: Naplnění dokumentů daty z databáze'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents, populating with data
- data, adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4ec56ae4345405cfc704a97ec624f9c2e4d96a5b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967908"
---
# <a name="how-to-populate-documents-with-data-from-a-database"></a>Postupy: Naplnění dokumentů daty z databáze

Stejným způsobem, že přistupujete k datům v projektech Windows Forms můžou k datům v projektech na úrovni dokumentu pro aplikace Microsoft Office. Použít stejné nástroje a kódu k načítání dat z databáze do vašeho řešení a ovládací prvky Windows Forms slouží k zobrazení data.

Kromě toho můžete zobrazit data pomocí hostitelské ovládací prvky. Hostitelské ovládací prvky jsou nativních objektů v aplikaci Microsoft Office Word, které je vylepšené o události a datové vazby funkce. Další informace najdete v tématu [hostovat položky a hostujte Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).

[!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]

Následující příklad ukazuje, jak přidat ovládací prvky vázané na data v projekty na úrovni dokumentu pomocí návrháře. Příklad toho, jak přidat ovládací prvky vázané na data v projekty doplňku VSTO v době běhu, naleznete v tématu [názorný postup: Jednoduché datové vazby v projektu doplňku VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).

![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [vytvoření vazby dat k obsahu aplikace Word 2007 řídí pomocí Visual Studio Tools pro systém Office (3.0)](http://go.microsoft.com/fwlink/?LinkId=136785).

## <a name="add-a-control-to-a-document-at-design-time"></a>Přidání ovládacího prvku na dokument v době návrhu

### <a name="to-populate-a-document-with-data-from-a-database"></a>K naplnění dokumentů daty z databáze

1. Otevřete projekt úrovni dokumentu aplikace Word v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], v Návrháři otevřený dokument.

2. Otevřít **zdroje dat** okno a vytvořit zdroj dat z databáze. Další informace najdete v tématu [přidat nové připojení](../data-tools/add-new-connections.md).

3. Přetáhněte pole ze **zdroje dat** okno dokumentu.

Ovládací prvek obsahu se přidá do dokumentu. Typ obsahu ovládacího prvku závisí na typu dat pole, které jste vybrali. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).

Můžete přidat jiného ovládacího prvku tak, že vyberete datové pole v **zdroje dat** okno a následným výběrem jiného ovládacího prvku z rozevíracího seznamu.

## <a name="objects-in-the-project"></a>Objekty v projektu

Kromě ovládacího prvku jsou následující objekty související s daty automaticky přidány do projektu:

- Typové datové sady, který zapouzdřuje tabulek dat, které jste se připojili v databázi. Další informace najdete v tématu [datovou sadu nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md).

- A <xref:System.Windows.Forms.BindingSource> ovládacího prvku, která se připojuje k typové datové sady. Další informace najdete v tématu [přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview).

- TableAdapter, který se připojuje k databázi typové datové sady. Další informace najdete v tématu [vytvoření a konfigurace objektů TableAdapter](../data-tools/create-and-configure-tableadapters.md).

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
- [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Použití místních souborů databáze v přehled řešení pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview)