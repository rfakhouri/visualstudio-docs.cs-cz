---
title: 'Postupy: Programové přidání řádků a sloupců do tabulek aplikace Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 780d794874ae87f3310810f2b46127fdf2eb46c5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419585"
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>Postupy: Programové přidání řádků a sloupců do tabulek aplikace Word
  V tabulce aplikace Microsoft Office Word buňky jsou uspořádány do řádků a sloupců. Můžete použít <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Rows> objektu pro přidání řádků do tabulky a <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Columns> objektu, který chcete přidat sloupce.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="document-level-customization-examples"></a>Příklady přizpůsobení na úrovni dokumentu
 Následující příklady kódu je možné v přizpůsobení na úrovni dokumentu. Pokud chcete použít tyto příklady, spustit je z `ThisDocument` třídu ve vašem projektu. Tyto příklady předpokládají, že dokument související s přizpůsobením již má alespoň jednu tabulku.

> [!IMPORTANT]
> Tento kód se spustí jenom v projektech, které vytvoříte pomocí některého z následujících šablon projektu:
>
> - Dokument aplikace Word 2013
> - Šablona pro Word 2013
> - Dokument aplikace Word 2010
> - Šablona aplikace Word 2010
>
>   Pokud chcete k provedení této úlohy v jakýkoli jiný typ projektu, je nutné přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení k přidávání řádků a sloupců do tabulek. Další informace najdete v tématu [jak: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na primární spolupracující sestavení aplikace Word 2010](http://go.microsoft.com/fwlink/?LinkId=189588).

### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky

1. Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda pro přidání řádku do tabulky.

     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]

### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupec do tabulky

1. Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce mají stejnou šířku.

     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]

## <a name="vsto-add-in-examples"></a>Příklady doplňku VSTO
 Můžete použít následující příklady kódu v doplňku VSTO. Pokud chcete použít příklady, spusťte z `ThisAddIn` třídu ve vašem projektu. Tyto příklady předpokládají, že aktivní dokument už má alespoň jednu tabulku.

> [!IMPORTANT]
> Tento kód se spustí jenom v projektech, které vytvoříte pomocí šablony doplňků VSTO pro Word.
>
> Pokud chcete k provedení této úlohy v jakýkoli jiný typ projektu, je nutné přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení k přidávání řádků a sloupců do tabulek. Další informace najdete v tématu [jak: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na primární spolupracující sestavení aplikace Word 2010](http://go.microsoft.com/fwlink/?LinkId=189588).

### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky

1. Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda pro přidání řádku do tabulky.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]

### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupec do tabulky

1. Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce mají stejnou šířku.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]

## <a name="see-also"></a>Viz také:
- [Postupy: Vytváření tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-create-word-tables.md)
- [Postupy: Přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)
- [Postupy: Vkládání kódu programu s vlastností dokumentu do tabulek aplikace Word](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)
