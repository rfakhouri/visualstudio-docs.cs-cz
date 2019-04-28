---
title: 'Postupy: Naplnění dokumentů daty z objektů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- data [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7cb221715ef1c2a50bc60e1725db3b1d8721f165
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967719"
---
# <a name="how-to-populate-documents-with-data-from-objects"></a>Postupy: Naplnění dokumentů daty z objektů

Accesing data do datového objektu funguje stejně v projektech na úrovni dokumentu pro aplikaci Microsoft Office Word stejně jako v projektech Windows Forms. Použít stejné nástroje a kódu k načítání dat z objektu do vašeho řešení a ovládací prvky Windows Forms slouží k zobrazení data. Kromě toho můžete zobrazit data pomocí hostitelské ovládací prvky. Hostitelské ovládací prvky jsou nativních objektů v aplikaci Microsoft Office Word, které je vylepšené o události a datové vazby funkce. Další informace najdete v tématu [hostovat položky a hostujte Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).

[!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

Je třeba provést tři základní kroky k naplnění dokumentů daty z objektu:

- Přidejte ovládací prvek v dokumentu, který můžete vázat na data.

- Přidání datového objektu do dokumentu.

- Připojte datový objekt k objektu BindingSource.

## <a name="to-add-a-data-object"></a>Chcete-li přidat datový objekt

Chcete-li přidat datový objekt, otevřete **zdroje dat** okno a vytvořit zdroj dat z objektu. Další informace najdete v tématu [přidat nové zdroje dat](../data-tools/add-new-data-sources.md).

## <a name="connect-the-data-object-to-the-bindingsource"></a>Připojit datový objekt k objektu BindingSource

V projektech na úrovni dokumentu přidání ovládacích prvků do dokumentu a svázat ho k datům v době návrhu.

V projekty doplňků VSTO vytvořit ovládací prvky a svázat ho v době běhu.

### <a name="document-level-projects"></a>Projekty na úrovni dokumentu

Připojení datového objektu do objektu BindingSource:

1. Přetáhněte datové pole, které chcete **zdroje dat** okno dokumentu. Tím se automaticky vytvoří ovládací prvek.

2. Ve vašem kódu vytvořte instanci typu, který jste zvolili pro zdroj dat objektu.

3. Instance, kterou chcete přiřadit <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.

### <a name="application-level-projects"></a>Projekty na úrovni aplikace

Připojení datového objektu do objektu BindingSource:

1. Ve vašem kódu vytvořte instanci typu, který je přidružený zdroj dat objektu.

2. Vytvoření instance <xref:System.Windows.Forms.BindingSource>.

3. Přiřazení instance zdroje dat k <xref:System.Windows.Forms.BindingSource.DataSource%2A> vlastnost <xref:System.Windows.Forms.BindingSource>.

4. Přidáte zdroj dat jako vázání dat na ovládací prvek.

## <a name="see-also"></a>Viz také:

- [Přidání nových zdrojů dat](../data-tools/add-new-data-sources.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Postupy: Naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview)