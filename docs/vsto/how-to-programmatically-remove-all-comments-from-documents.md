---
title: 'Postupy: Programově odstraňování všech komentářů z dokumentů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 368779aa5c0edbfcaba3aff2abdf3eba09375f9f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53833407"
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>Postupy: Programově odstraňování všech komentářů z dokumentů
  Použití `DeleteAllComments` metoda všech komentářů z dokumentů Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>Chcete odstranit všechny komentáře z dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> metodu `ThisDocument` třídu ve vašem projektu. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]  
  
## <a name="to-remove-all-comments-from-a-document-by-using-a-vsto-add-in"></a>Chcete odstranit všechny komentáře z dokumentu s použitím doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> ze kterého chcete odebrat komentáře.  
  
     Následující příklad odebere všechny komentáře v aktivním dokumentu. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Přidávání komentáře k textu dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)  
