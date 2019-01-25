---
title: Programová omezení hostitelských položek a hostitelských ovládacích prvků
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, host controls
- application development [Office development in Visual Studio], host items
- Office applications [Office development in Visual Studio], host items
- host items [Office development in Visual Studio], programmatic limitations
- Excel [Office development in Visual Studio], host items
- host controls [Office development in Visual Studio], creating
- document-level customizations [Office development in Visual Studio], host controls
- Office applications [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- controls [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], passing to methods and properties
- application development [Office development in Visual Studio], host controls
- Excel [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], programmatic limitations
- documents [Office development in Visual Studio], host items
- Office documents [Office development in Visual Studio, host items
- Word [Office development in Visual Studio], host items
- document-level customizations [Office development in Visual Studio], host items
- Word [Office development in Visual Studio], host controls
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: facf78a9c737dbaa0d3a48e93d8424d5288f683a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865460"
---
# <a name="programmatic-limitations-of-host-items-and-host-controls"></a>Programová omezení hostitelských položek a hostitelských ovládacích prvků
  Každý hostitelský objekt a hostitelský ovládací prvek slouží k chovat jako odpovídající nativní aplikace Microsoft Office Word nebo Microsoft Office Excel objektu s dalšími funkcemi. Existují však některé základní rozdíly v chování hostitelských položek a hostitelských ovládacích prvků a nativních objektů Office za běhu.  
  
 Obecné informace o hostitelských položek a hostitelských ovládacích prvků naleznete v tématu [hostovat položky a hostujte Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="programmatically-create-host-items"></a>Vytváření položek hostitele prostřednictvím kódu programu  
 Když prostřednictvím kódu programu vytvořit nebo otevřít dokument, sešit nebo list za běhu pomocí objektového modelu aplikace Word nebo Excel, položka není položkou hostitele. Místo toho tento nový objekt je nativní objekt Office. Například, pokud použijete <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> metodu pro vytvoření nového dokumentu aplikace Word v běhu, bude se jednat o nativní <xref:Microsoft.Office.Interop.Word.Document> objekt spíše než <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt. Podobně, když vytvoříte nový list za běhu pomocí <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> metoda, získáte nativní <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt spíše než <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt.  
  
 V projektech na úrovni dokumentu nelze vytvořit položky hostitele v době běhu. Hostitelské položky lze vytvořit pouze v době návrhu v projektech na úrovni dokumentu. Další informace najdete v tématu [hostitelská položka Document](../vsto/document-host-item.md), [hostitelská položka Workbook](../vsto/workbook-host-item.md), a [hostitelská položka Worksheet](../vsto/worksheet-host-item.md).  
  
 Na projekty doplňku VSTO, můžete vytvořit <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, nebo <xref:Microsoft.Office.Tools.Excel.Worksheet> hostovat položky v době běhu. Další informace najdete v tématu [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="programmatically-create-host-controls"></a>Hostitelské ovládací prvky vytváření prostřednictvím kódu programu  
 Můžete programově přidat hostitelské ovládací prvky na <xref:Microsoft.Office.Tools.Word.Document> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt za běhu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Hostitelské ovládací prvky nelze přidat do nativní <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Worksheet>.  
  
> [!NOTE]  
>  Následující hostitelské ovládací prvky nelze programově přidat na listech nebo dokumenty: <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, a <xref:Microsoft.Office.Tools.Word.XMLNodes>.  
  
## <a name="understand-type-differences-between-host-items-host-controls-and-native-office-objects"></a>Pochopení typů rozdíly mezi hostitelské položky, hostitelské ovládací prvky a nativních objektů sady Office  
 Pro každý hostitelský objekt a hostitelského ovládacího prvku je základní nativní objekt aplikace Microsoft Office Word nebo Microsoft Office Excel. Základní objekt můžete přistupovat pomocí vlastnosti InnerObject položky hostitele nebo hostitelského ovládacího prvku. Neexistuje však žádný způsob, jak přetypovat na nativní objekt Office její odpovídající položka hostitele nebo hostitelského ovládacího prvku. Pokud se pokusíte nativní objekt Office přetypování na typ položky hostitele nebo hostitelského ovládacího prvku, <xref:System.InvalidCastException> je vyvolána výjimka.  
  
 Existuje několik scénářů, ve kterém rozdíly mezi typy hostitelských položek a hostitelských ovládacích prvků a nativní objekty Office může ovlivnit váš kód.  
  
### <a name="pass-host-controls-to-methods-and-properties"></a>Předání hostitelské ovládací prvky do metody a vlastnosti  
 V aplikaci Word nelze předat hostitelského ovládacího prvku metodu nebo vlastnost, která vyžaduje nativní objekt slova jako parametr. Musíte použít vlastnost InnerObject hostitelského ovládacího prvku se vraťte na základní objekt nativní aplikace Word. Například můžete předat <xref:Microsoft.Office.Interop.Word.Bookmark> objekt metody předáním <xref:Microsoft.Office.Tools.Word.Bookmark.InnerObject%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Bookmark> hostování ovládacího prvku v metodě.  
  
 V aplikaci Excel musíte použít vlastnost InnerObject hostitelského ovládacího prvku předat metody nebo vlastnosti hostitelského ovládacího prvku při metodu nebo vlastnost očekává, že základní objekt aplikace Excel.  
  
 Následující příklad vytvoří <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit a předává jej do <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metody. Tento kód použije <xref:Microsoft.Office.Tools.Excel.NamedRange.InnerObject%2A> vlastnost pojmenované oblasti vrátit základní Office <xref:Microsoft.Office.Interop.Excel.Range> , který vyžaduje <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metody.  
  
 [!code-csharp[Trin_VstcoreHostControlsExcel#28](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#28)]
 [!code-vb[Trin_VstcoreHostControlsExcel#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#28)]  
  
### <a name="return-types-of-native-office-methods-and-properties"></a>Návratové typy nativní Office metod a vlastností  
 Většina metod a vlastností položek hostitele vrátí základní nativní objekt Office, na kterém je založena hostitelský objekt. Například <xref:Microsoft.Office.Tools.Excel.NamedRange.Parent%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.NamedRange> hostování ovládacího prvku v aplikaci Excel vrátí <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt spíše než <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt. Podobně <xref:Microsoft.Office.Tools.Word.RichTextContentControl.Parent%2A> vlastnost <xref:Microsoft.Office.Tools.Word.RichTextContentControl> hostování ovládacího prvku v aplikaci Word vrátí <xref:Microsoft.Office.Interop.Word.Document> objekt spíše než <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt.  
  
### <a name="access-collections-of-host-controls"></a>Přístup ke kolekcím hostitelské ovládací prvky  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Neposkytuje jednotlivých kolekcí pro každý typ hostitelského ovládacího prvku. Místo toho použijte vlastnost Controls prvku hostitelská položka k iteraci v rámci všech spravovaných ovládacích prvků (hostitelské ovládací prvky a ovládací prvky Windows Forms) v dokumentu nebo listu a potom vyhledejte položky, které odpovídají typu hostitelského ovládacího prvku, které vás zajímají. Následující příklad kódu zkontroluje každý ovládací prvek ve Wordovém dokumentu a určuje, zda je ovládací prvek <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
 [!code-csharp[Trin_VstcoreHostControlsWord#10](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#10)]
 [!code-vb[Trin_VstcoreHostControlsWord#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#10)]  
  
 Další informace o vlastnosti ovládacích prvků položek hostitele, naleznete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Modely objektů aplikace Word a Excel patří vlastnosti, které zveřejňují kolekce nativních ovládacích prvků na dokumenty a sešity. Spravované ovládací prvky nelze přistupovat pomocí těchto vlastností. Například není možné vytvořit výčet každý <xref:Microsoft.Office.Tools.Word.Bookmark> hostování ovládacího prvku v dokumentu s použitím <xref:Microsoft.Office.Interop.Word._Document.Bookmarks%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Tools.Word.Document.Bookmarks%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Document>. Tyto vlastnosti obsahovat pouze <xref:Microsoft.Office.Interop.Word.Bookmark> ovládací prvky v dokumentu; neobsahují <xref:Microsoft.Office.Tools.Word.Bookmark> hostovat ovládací prvky v dokumentu.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Hostitelská položka Workbook](../vsto/workbook-host-item.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)  
