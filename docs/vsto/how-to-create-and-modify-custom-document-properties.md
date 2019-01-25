---
title: 'Postupy: Vytvoření a změny přizpůsobených vlastností dokumentu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e890cedb774527ba49c6061ee36c5efc091f3188
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865811"
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>Postupy: Vytvoření a změny přizpůsobených vlastností dokumentu
  Aplikace Microsoft Office výše uvedených poskytují předdefinované vlastnosti, které jsou uloženy s dokumenty. Kromě toho můžete vytvořit a změny přizpůsobených vlastností dokumentu, pokud nejsou k dispozici další informace, které chcete uložit s dokumentem.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
 Použijte vlastnost CustomDocumentProperties dokumentu pro práci s vlastními vlastnostmi. Například v projektu na úrovni dokumentu pro aplikaci Microsoft Office Excel, použijte <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> vlastnost `ThisWorkbook` třídy. V projekt doplňku VSTO pro Excel pomocí <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Workbook> objektu. Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, což je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnost kolekce, kterou chcete načíst určité vlastnosti, podle názvu nebo podle indexu v rámci kolekce.  
  
 Následující příklad ukazuje, jak přidat vlastní vlastnost v přizpůsobení na úrovni dokumentu pro Excel a přiřaďte mu hodnotu.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Přístup k a manipulaci s vlastní vlastnosti dokumentu v aplikaci Microsoft Word? ](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
## <a name="example"></a>Příklad  
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]  
  
## <a name="robust-programming"></a>Robustní programování  
 Při pokusu o přístup `Value` vlastnost nedefinovanými vlastnostmi vyvolá výjimku.  
  
## <a name="see-also"></a>Viz také:  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Postupy: Čtení a zápis do vlastnosti dokumentu](../vsto/how-to-read-from-and-write-to-document-properties.md)  
