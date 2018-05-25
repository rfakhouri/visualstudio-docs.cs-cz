---
title: 'Postupy: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- PowerPoint [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
- application-level add-ins [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 803a0c146bbf17ee79f79fe5de95fdf2ee2151da
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins"></a>Postupy: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO
  V následujících typech dokumentů můžete ukládat XML data tak, že vytvoříte vlastní část XML v doplňku VSTO:  
  
-   Sešitu aplikace Microsoft Office Excel.  
  
-   Dokument aplikace Microsoft Office Word.  
  
-   Aplikace Microsoft Office PowerPoint.  
  
 Další informace najdete v tématu [přehled částí XML vlastní](../vsto/custom-xml-parts-overview.md).  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty na úrovni aplikace pro aplikaci Excel, PowerPoint a Word. Další informace najdete v tématu [dostupné funkce podle aplikace a projekt typu Office](../vsto/features-available-by-office-application-and-project-type.md).  
  
## <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Chcete-li přidat vlastní část XML do sešitu aplikace Excel  
  
1.  Přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> do objektu <xref:Microsoft.Office.Interop.Excel._Workbook.CustomXMLParts%2A> kolekce v sešitu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v sešitu.  
  
     Následující příklad kódu přidá k zadané sešitu na vlastní část XML.  
  
     [!code-vb[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/VisualBasic/trin_addcustomxmlpartexcelapplevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelAppLevel/ThisAddIn.cs#1)]  
  
2.  Přidat `AddCustomXmlPartToWorkbook` metodu `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
3.  Volejte metodu z jiných kódu v projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře sešitu, volat z obslužné rutiny události pro metodu <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> událostí.  
  
## <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Přidat na vlastní část XML do dokumentů aplikace Word  
  
1.  Přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> do objektu <xref:Microsoft.Office.Interop.Word._Document.CustomXMLParts%2A> kolekce v dokumentu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v dokumentu.  
  
     Následující příklad kódu přidá na vlastní část XML do zadaný dokument.  
  
     [!code-vb[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.cs#1)]  
  
2.  Přidat `AddCustomXmlPartToDocument` metodu `ThisAddIn` – třída v projektu doplňku VSTO ve Wordu.  
  
3.  Volejte metodu z jiných kódu v projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře dokument, volat z obslužné rutiny události pro metodu <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> událostí.  
  
## <a name="to-add-a-custom-xml-part-to-a-powerpoint-presentation"></a>Přidat na vlastní část XML do Powerpointovou prezentaci.  
  
1.  Přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> do objektu <xref:Microsoft.Office.Interop.PowerPoint._Presentation.CustomXMLParts%2A> kolekce v prezentaci. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v prezentaci.  
  
     Následující příklad kódu přidá do zadaného prezentace na vlastní část XML.  
  
     [!code-csharp[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.vb#1)]  
  
2.  Přidat `AddCustomXmlPartToPresentation` metodu `ThisAddIn` – třída v projektu doplňku VSTO pro PowerPoint.  
  
3.  Volejte metodu z jiných kódu v projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře prezentace, volat z obslužné rutiny události pro metodu <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterPresentationOpen> událostí.  
  
## <a name="robust-programming"></a>Robustní programování  
 Pro zjednodušení tento příklad používá řetězec XML, který je definován jako místní proměnné v metodě. Obvykle opatřete si kód XML z externího zdroje, jako je například soubor nebo databázi.  
  
## <a name="see-also"></a>Viz také  
 [Přehled vlastních částí XML](../vsto/custom-xml-parts-overview.md)   
 [Postupy: Přidání vlastních částí XML do přizpůsobení na úrovni dokumentu](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
  