---
title: "Postupy: vytváření a změny přizpůsobených vlastností dokumentu | Microsoft Docs"
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
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
ms.assetid: 99d9dfaf-891f-4f3b-a580-67362afdaf34
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1ab68f9bd5c6a6bc1176fc211b99ad1de777ca38
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  