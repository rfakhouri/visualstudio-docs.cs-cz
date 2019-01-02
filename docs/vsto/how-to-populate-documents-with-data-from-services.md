---
title: 'Postupy: Naplnění dokumentů daty ze služeb'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- Web services [Office development in Visual Studio], populating documents
- data [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: e935501e2e38c7e6c3abdb1c16e351342cf52a8a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838291"
---
# <a name="how-to-populate-documents-with-data-from-services"></a>Postupy: Naplnění dokumentů daty ze služeb

Přístup k datům funguje stejně v projektech na úrovni dokumentu pro aplikace Microsoft Office stejně jako v projektech Windows Forms. Použít stejné nástroje a kódu přenést data do vašeho řešení a ovládací prvky Windows Forms můžete použít i pro zobrazení údajů. Kromě toho můžete využít výhod ovládací prvky hostitelské ovládací prvky, které jsou nativních objektů v aplikaci Microsoft Office Excel a Microsoft Office Word, které je vylepšené o události a datové vazby funkce volána. Další informace najdete v tématu [hostovat položky a hostujte Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).

[!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

Následující příklad ukazuje, jak přidat ovládací prvky vázaných dat na dokumenty v době návrhu. Příklad toho, jak přidat ovládací prvky vázané na data v doplňcích VSTO za běhu, naleznete v tématu [názorný postup: Vytvoření vazby k datům ze služby v projektu doplňku VSTO](../vsto/walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project.md).

![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Interakci s webovými službami z Microsoft Excelu? ](http://go.microsoft.com/fwlink/?LinkID=130284).

## <a name="to-populate-a-document-level-project-with-data-from-a-web-service"></a>K naplnění úrovni dokumentu projektu s daty z webové služby

1.  Otevřít **zdroje dat** okna a vytvořte zdroj dat služby pro váš projekt. Další informace najdete v tématu [přidat nové zdroje dat](../data-tools/add-new-data-sources.md).

2.  Přetáhněte tabulku nebo chcete, aby z pole **zdroje dat** okno dokumentu.

     Vytvoření ovládacího prvku na dokument, <xref:System.Windows.Forms.BindingSource> se vytvoří, který je vázán na objekt třídy ve vašem projektu a třídy jsou generovány pro službu.

3.  Ve vašem kódu vytvoření instance třídy webové služby, který jste se připojili v kroku 1.

4.  Pokud jsou vlastnosti, které jsou nutné pro komunikaci s webovou službou, vytváření instancí těchto vlastností.

5.  Vytvoření a odeslání požadavku na data pomocí metody vystavené objektem webové služby a všechny instance vlastnost, že kterou jste vytvořili v kroku 4.

     Metody, které použijete, závisí na jaké webové služby nabízí.

6.  Přiřadit data odpovědi z webové služby <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.

Při spuštění projektu ovládací prvky zobrazí první záznam ve zdroji dat. Posouvání záznamů se zpracováním událostí měny pomocí objektů v můžete povolit <xref:System.Windows.Forms.BindingSource>.

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Přidání nových zdrojů dat](../data-tools/add-new-data-sources.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Postupy: Naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [Postupy: Naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Postupy: Naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)