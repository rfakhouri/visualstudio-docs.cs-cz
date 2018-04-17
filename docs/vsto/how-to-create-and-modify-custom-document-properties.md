---
title: 'Postupy: vytváření a změny přizpůsobených vlastností dokumentu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8c997fbe764ba355d16def278c9beda8c177faed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>Postupy: Vytváření a změny přizpůsobených vlastností dokumentu
  Aplikace Microsoft Office, které jsou uvedené výše zadejte předdefinované vlastnosti, které jsou uloženy s dokumenty. Kromě toho můžete vytvořit a upravit vlastní vlastnosti dokumentu, pokud nejsou další informace, které chcete k uložení dokumentu v platnosti.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
 Použijte vlastnost CustomDocumentProperties dokumentu pro práci s vlastní vlastnosti. Například v projektu úrovni dokumentu pro aplikaci Microsoft Office Excel použít <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> vlastnost `ThisWorkbook` třídy. V doplňku VSTO projektu pro aplikaci Excel, pomocí <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Workbook> objektu. Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, který je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnosti kolekce pro načtení určité vlastnosti, pomocí názvu nebo podle indexu v kolekci.  
  
 Následující příklad ukazuje, jak přidat vlastní vlastnosti v přizpůsobení na úrovni dokumentu pro Excel a přiřaďte ho hodnotu.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: přístup a upravit vlastnosti vlastní dokumentu v Microsoft Wordu?](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
## <a name="example"></a>Příklad  
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]  
  
## <a name="robust-programming"></a>Robustní programování  
 Při pokusu o přístup `Value` vlastnost pro nedefinované vlastnosti vyvolá výjimku.  
  
## <a name="see-also"></a>Viz také  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Postupy: Čtení z vlastností dokumentu a zápis do nich](../vsto/how-to-read-from-and-write-to-document-properties.md)  
  
  