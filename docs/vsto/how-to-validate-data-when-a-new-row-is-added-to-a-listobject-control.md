---
title: "Postupy: ověření dat při přidání nového řádku do ovládacího prvku ListObject | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], validating data
- ListObject control, new row
- ListObject control, validating data
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 509d298dc3ac10a91f2eb10aa8bcb26a9738f4d4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control"></a>Postupy: Ověření dat při přidání nového řádku do ovládacího prvku ListObject
  Uživatele můžete přidat nové řádky, které <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který je vázaný na data. Před potvrzením změny ke zdroji dat můžete ověřit data uživatele.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="data-validation"></a>Ověřování dat  
 Vždy, když se přidá řádek do <xref:Microsoft.Office.Tools.Excel.ListObject> k datům, která je vázaná <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> událost se vyvolá. Dokáže zpracovat tuto událost, chcete-li provést ověření vaše data. Například pokud vaše aplikace vyžaduje, že lze přidat pouze zaměstnanci věku 18 do 65 ke zdroji dat, můžete ověřit, že stáří zadali spadá do rozsahu předtím, než se přidá řádek.  
  
> [!NOTE]  
>  Vždy byste měli zkontrolovat vstup uživatele na serveru kromě klienta. Další informace najdete v tématu [zabezpečit klientské aplikace](/dotnet/framework/data/adonet/secure-client-applications).  
  
#### <a name="to-validate-data-when-a-new-row-is-added-to-data-bound-listobject"></a>Pro ověření dat při nový řádek je přidat do vázané na data ListObject  
  
1.  Vytváření proměnných pro ID a <xref:System.Data.DataTable> na úrovni třídy.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#8)]  
  
2.  Vytvořte novou <xref:System.Data.DataTable> a přidejte ukázkový sloupce a data v `Startup` obslužnou rutinu události `Sheet1` – třída (v projektech na úrovni dokumentu) nebo `ThisAddIn` – třída (v projektu doplňku VSTO).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#9)]  
  
3.  Přidejte kód, který `list1_BeforeAddDataBoundRow` obslužné rutiny události zkontrolujte, zda zadaný stáří spadá do přijatelný rozsah.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#10)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu předpokládá, že máte existující <xref:Microsoft.Office.Tools.Excel.ListObject> s názvem `list1` na listu, ve kterém se zobrazí tento kód.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Postupy: Mapování sloupců objektu ListObject na data](../vsto/how-to-map-listobject-columns-to-data.md)  
  
  