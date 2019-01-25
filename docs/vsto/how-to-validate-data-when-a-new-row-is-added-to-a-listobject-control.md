---
title: 'Postupy: Ověření dat při přidání nového řádku do ovládacího prvku ListObject'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], validating data
- ListObject control, new row
- ListObject control, validating data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4820acb20b8eadfd79b3d2a22714dbfee5a75cb7
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862353"
---
# <a name="how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control"></a>Postupy: Ověření dat při přidání nového řádku do ovládacího prvku ListObject
  Uživatelé můžou přidávat nové řádky <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který je vázán na data. Před potvrzením změny do zdroje dat. můžete ověřit data uživatele.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="data-validation"></a>Ověřování dat  
 Vždy, když se přidá řádek do <xref:Microsoft.Office.Tools.Excel.ListObject> , který je vázán na data, <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> událost se vyvolá. Tato událost provádět ověřování dat dokáže zpracovat. Pokud vaše aplikace vyžaduje, že lze přidat pouze zaměstnanci ve věku 18 až 65 ke zdroji dat, ověřte například, že věk zadali spadá do rozsahu před přidáním řádku.  
  
> [!NOTE]  
>  Vždy byste měli zkontrolovat vstupu uživatele na serveru kromě klienta. Další informace najdete v tématu [zabezpečené klientské aplikace](/dotnet/framework/data/adonet/secure-client-applications).  
  
### <a name="to-validate-data-when-a-new-row-is-added-to-data-bound-listobject"></a>Ověření dat při nový řádek je přidat do vázané na data ListObject  
  
1.  Vytvoření proměnné pro ID a <xref:System.Data.DataTable> na úrovni třídy.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#8)]  
  
2.  Vytvořte nový <xref:System.Data.DataTable> a přidejte ukázkový sloupce a data v `Startup` obslužná rutina události `Sheet1` třídy (v projektu úrovni dokumentu) nebo `ThisAddIn` třídy (v projektu doplňku VSTO).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#9)]  
  
3.  Přidejte kód, který `list1_BeforeAddDataBoundRow` obslužná rutina události ke kontrole, jestli stáří zadali spadá do přijatelný rozsah.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#10)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad kódu předpokládá, že už máte existující <xref:Microsoft.Office.Tools.Excel.ListObject> s názvem `list1` na listu, ve kterém se zobrazí tento kód.  
  
## <a name="see-also"></a>Viz také:  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Postupy: Mapování sloupců objektu ListObject na data](../vsto/how-to-map-listobject-columns-to-data.md)  
