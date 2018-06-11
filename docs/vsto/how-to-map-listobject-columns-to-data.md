---
title: 'Postupy: sloupců objektu ListObject mapy k datům'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], mapping to ListObject column
- ListObject control, mapping data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 12c1fe0c631c31d7f502ae967cbea90b0cc81d6e
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255441"
---
# <a name="how-to-map-listobject-columns-to-data"></a>Postupy: sloupců objektu ListObject mapy k datům
  Po vytvoření vazby <xref:Microsoft.Office.Tools.Excel.ListObject> řídit k <xref:System.Data.DataTable>, možná nebudete chtít zobrazit všechny sloupce v seznamu, nebo může mít některé sloupce, které nejsou vázané na data. Můžete namapovat sloupce, které se má zobrazit v <xref:Microsoft.Office.Tools.Excel.ListObject> při volání <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> metoda.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak I: vytvořit seznam v aplikaci Excel, která je připojena k seznamu služby SharePoint?](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
## <a name="map-columns"></a>Mapování sloupců  
  
### <a name="to-map-a-data-table-to-columns-in-a-list"></a>Mapovat tabulku dat sloupce v seznamu.  
  
1.  Vytvořte <xref:System.Data.DataTable> na úrovni třídy.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]  
  
2.  Přidání sloupců ukázka a dat v `Startup` obslužnou rutinu události `Sheet1` – třída (v projektech na úrovni dokumentu) nebo `ThisAddIn` – třída (v projektu doplňku VSTO).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]  
  
3.  Volání <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> metoda a předejte jí názvy sloupců v pořadí, v jakém se mají zobrazit. Objekt seznamu bude navázán nově vytvořené <xref:System.Data.DataTable>, ale pořadí sloupců v seznamu objektu, se budou lišit od pořadí se objeví v <xref:System.Data.DataTable>.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]  
  
## <a name="specify-unmapped-columns"></a>Zadejte nemapované sloupce  
 Při mapování sloupců <xref:System.Data.DataTable>, můžete také určit, že některé sloupce by neměla být vázána k datům předávání prázdný řetězec. Nový sloupec, který není vázán na data se pak přidá do <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku.  
  
### <a name="to-specify-an-unmapped-column-when-mapping-listobject-columns"></a>Chcete-li určit sloupec nenamapovaný při mapování sloupců objektu ListObject  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> metoda a předejte jí názvy sloupců v pořadí, v jakém se mají zobrazit. Používá se k označení, kde se má přidat nenamapovaný sloupec; prázdný řetězec. v takovém případě mezi sloupci Název a poslední název sloupce.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad kódu předpokládá, že už máte existující <xref:Microsoft.Office.Tools.Excel.ListObject> s názvem `list1` na listu, ve kterém se zobrazí tento kód.  
  
## <a name="see-also"></a>Viz také:  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Postupy: vyplnění ListObject ovládací prvky s daty](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)  
  
  