---
title: Použití ovládacích prvků Windows Forms na listech aplikace Excel
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Windows Forms controls [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Window Forms controls
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 032ee551ff04590ccdb8744c1274b137dec0b756
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62982323"
---
# <a name="use-windows-forms-controls-on-excel-worksheets"></a>Použití ovládacích prvků Windows Forms na listech aplikace Excel
  Můžete přidat ovládací prvky Windows Forms do sešitů aplikace Microsoft Office Excel stejným způsobem, že přidáte ovládací prvky Windows Forms. Obecné informace o práci s ovládacími prvky v dokumentech, najdete v části [ovládací prvky Windows Forms v přehledu dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="control-considerations-for-excel"></a>Důležité informace o ovládací prvek pro Excel
 Existuje několik důležitých informací, které jsou specifické pro aplikaci Excel.

### <a name="match-control-size-to-cell-size"></a>Velikost ovládacího prvku na velikost buňky
 Můžete nastavit ovládací prvek změnit velikost automaticky při změně velikosti nadřazené buňky. Další informace najdete v tématu [jak: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md).

### <a name="add-components-that-are-shared-by-all-worksheets"></a>Přidat součásti, které jsou sdíleny ve všech listů
 Můžete přidat komponenty, které chcete sdílet mezi všechny listy, například <xref:System.Data.DataSet>, do návrháře sešitu místo do listů. Součást se zobrazí v panelu komponent.

### <a name="formula-for-embedding-controls"></a>Vzorec pro vkládání ovládacích prvků
 Když vyberete ovládací prvek v aplikaci Excel, zobrazí se **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nutné a by neměl být odstraněn.

## <a name="see-also"></a>Viz také:
- [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)
- [Postupy: Skrytí ovládacích prvků na listech při tisku](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)
- [Návod: Změna formátování listů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)
- [Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)
- [Návod: Aktualizace grafu na listu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)
