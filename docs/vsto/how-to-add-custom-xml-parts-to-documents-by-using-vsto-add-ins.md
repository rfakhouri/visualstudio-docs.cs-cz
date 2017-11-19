---
title: "Postupy: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- PowerPoint [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
- application-level add-ins [Office development in Visual Studio], custom XML parts
ms.assetid: 872d2beb-193b-49f9-9a7b-dcebab91a73b
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e851c0dcdbb3ed86dcf4a303cc1ad26b65035bc8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins"></a>Návody: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO
  V následujících typech dokumentů můžete ukládat XML data tak, že vytvoříte vlastní část XML v doplňku VSTO:  
  
-   Sešitu aplikace Microsoft Office Excel.  
  
-   Dokument aplikace Microsoft Office Word.  
  
-   Aplikace Microsoft Office PowerPoint.  
  
 Další informace najdete v tématu [přehled částí XML vlastní](../vsto/custom-xml-parts-overview.md).  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty na úrovni aplikace pro aplikaci Excel, PowerPoint a Word. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Chcete-li přidat vlastní část XML do sešitu aplikace Excel  
  
1.  Přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> do objektu <xref:Microsoft.Office.Interop.Excel._Workbook.CustomXMLParts%2A> kolekce v sešitu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v sešitu.  
  
     Následující příklad kódu přidá k zadané sešitu na vlastní část XML.  
  
     [!code-vb[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/VisualBasic/trin_addcustomxmlpartexcelapplevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelAppLevel/ThisAddIn.cs#1)]  
  
2.  Přidat `AddCustomXmlPartToWorkbook` metodu `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
3.  Volejte metodu z jiných kódu v projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře sešitu, volat z obslužné rutiny události pro metodu <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> událostí.  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Přidat na vlastní část XML do dokumentů aplikace Word  
  
1.  Přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> do objektu <xref:Microsoft.Office.Interop.Word._Document.CustomXMLParts%2A> kolekce v dokumentu. <xref:Microsoft.Office.Core.CustomXMLPart> Obsahuje řetězec XML, který chcete uložit v dokumentu.  
  
     Následující příklad kódu přidá na vlastní část XML do zadaný dokument.  
  
     [!code-vb[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.cs#1)]  
  
2.  Přidat `AddCustomXmlPartToDocument` metodu `ThisAddIn` – třída v projektu doplňku VSTO ve Wordu.  
  
3.  Volejte metodu z jiných kódu v projektu. Například pokud chcete vytvořit vlastní část XML, když uživatel otevře dokument, volat z obslužné rutiny události pro metodu <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> událostí.  
  
### <a name="to-add-a-custom-xml-part-to-a-powerpoint-presentation"></a>Přidat na vlastní část XML do Powerpointovou prezentaci.  
  
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
  
  