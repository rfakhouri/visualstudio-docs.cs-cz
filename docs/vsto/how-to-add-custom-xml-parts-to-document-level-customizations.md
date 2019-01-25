---
title: 'Postupy: Přidání vlastních částí XML do přizpůsobení na úrovni dokumentu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document-level customizations [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: eb87650156f5ed0060170b0b9f809924d2326fce
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868024"
---
# <a name="how-to-add-custom-xml-parts-to-document-level-customizations"></a>Postupy: Přidání vlastních částí XML do přizpůsobení na úrovni dokumentu
  V dokumentu aplikace Microsoft Office Word a sešit aplikace Microsoft Office Excel můžete ukládat XML data tak, že vytvoříte vlastní část XML do přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [přehled částí XML vlastní](../vsto/custom-xml-parts-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Visual Studio neposkytuje projekty na úrovni dokumentu pro aplikaci Microsoft Office PowerPoint. Informace o přidání vlastních částí XML do Powerpointovou prezentaci. pomocí doplňku VSTO najdete v tématu [jak: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md).  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Chcete-li přidat vlastní část XML k Excelovému sešitu  
  
1.  Přidat nový <xref:Microsoft.Office.Core.CustomXMLPart> objektu <xref:Microsoft.Office.Core.CustomXMLParts> kolekce v sešitu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v sešitu.  
  
     [!code-csharp[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.vb#1)]  
  
2.  Přidat `AddCustomXmlPartToWorkbook` metodu `ThisWorkbook` třídy v projektu úrovni dokumentu pro Excel.  
  
3.  Volejte metodu od jiného kódu ve vašem projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře sešit, volejte metodu z `ThisWorkbook_Startup` obslužné rutiny události.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Chcete-li přidat vlastní část XML do Wordového dokumentu  
  
1.  Přidat nový <xref:Microsoft.Office.Core.CustomXMLPart> objektu <xref:Microsoft.Office.Core.CustomXMLParts> kolekce v dokumentu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v dokumentu.  
  
     [!code-vb[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.cs#1)]  
  
2.  Přidat `AddCustomXmlPartToDocument` metodu `ThisDocument` třídy v projektu úrovni dokumentu pro aplikaci Word.  
  
3.  Volejte metodu od jiného kódu ve vašem projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře dokument, volejte metodu z `ThisDocument_Startup` obslužné rutiny události.  
  
## <a name="robust-programming"></a>Robustní programování  
 Pro zjednodušení tento příklad používá řetězec jazyka XML, který je definován jako místní proměnná v metodě. Obvykle byste měli získat XML z externího zdroje, jako je například soubor nebo databáze.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled vlastních částí XML](../vsto/custom-xml-parts-overview.md)   
 [Postupy: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
