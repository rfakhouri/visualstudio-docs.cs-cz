---
title: "Postupy: Programové přidávání komentářů k textu v dokumentech | Microsoft Docs"
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
- comments, adding to documents
- documents [Office development in Visual Studio], adding comments
ms.assetid: 4e396e31-01bf-424c-be6b-9a1806bcd572
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 69f320ef3e7b3914d9d6eadb7466b3a216ef95d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-comments-to-text-in-documents"></a>Postupy: Přidávání komentářů k textu dokumentů prostřednictvím kódu programu
  Vlastnost komentáře třídy dokumentu přidá komentář na rozsah textu v dokumentu aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Následující příklad přidá komentář prvním odstavci v dokumentu.  
  
### <a name="to-add-a-new-comment-to-text-in-a-document-level-customization"></a>Chcete-li přidat nový komentář na text v přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> metodu <xref:Microsoft.Office.Tools.Word.Document.Comments%2A> vlastností a zadejte rozsah a text poznámky. Chcete-li použít následující příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomation#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#118)]  
  
### <a name="to-add-a-new-comment-to-text-in-an-vsto-add-in"></a>Chcete-li přidat nový komentář na text v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Word.Comments.Add%2A> metodu <xref:Microsoft.Office.Interop.Word._Document.Comments%2A> vlastností a zadejte rozsah a text poznámky.  
  
     Následující příklad kódu přidá komentář pro aktivní dokument. Pokud chcete použít v tomto příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#118)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#118](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#118)]  
  
## <a name="robust-programming"></a>Robustní programování  
 Chcete-li změnit iniciály uživatele, které aplikace Word přidá do komentáře, použijte <xref:Microsoft.Office.Interop.Word._Application.UserInitials%2A> vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové odstraňování všech komentářů z dokumentů](../vsto/how-to-programmatically-remove-all-comments-from-documents.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)  
  
  