---
title: "Postupy: programové odstraňování všech komentářů z dokumentů | Microsoft Docs"
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
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4210a300b8ad39005dcb6584bdc0345a9424f0fe
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>Postupy: Odstraňování všech komentářů z dokumentů prostřednictvím kódu programu
  Pomocí této metody DeleteAllComments odstraňování všech komentářů z dokumentu aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>Chcete-li odebrat všechny komentáře z dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> metodu `ThisDocument` třídy ve vašem projektu. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]  
  
### <a name="to-remove-all-comments-from-a-document-by-using-an-vsto-add-in"></a>Chcete-li odebrat všechny komentáře z dokumentu pomocí doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> ze kterého chcete odebrat komentáře.  
  
     Následující příklad kódu odebere všechny komentáře aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Programové přidávání komentářů k textu v dokumentech](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)  
  
  