---
title: "Postupy: aktualizace textu záložek prostřednictvím kódu programu | Microsoft Docs"
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
- bookmarks, updating text
- text [Office development in Visual Studio], updating in bookmarks
- Bookmark control, updating contents
ms.assetid: 2324164d-2538-4695-9aaf-7285ce403be3
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6c9db34e05c964b95a41593b194c4941293c7efb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-update-bookmark-text"></a>Postupy: Aktualizace textu záložek prostřednictvím kódu programu
  Můžete vložit text do záložku zástupný symbol v dokumentu aplikace Microsoft Office Word tak, aby text můžete načíst později, nebo nahrazení textu v záložky. Pokud vyvíjíte přizpůsobení na úrovni dokumentu, můžete také aktualizovat v text <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek, který je vázaný na data. Další informace najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Objekt záložku může být jeden ze dvou typů:  
  
-   A <xref:Microsoft.Office.Tools.Word.Bookmark> hostování ovládacího prvku.  
  
     <xref:Microsoft.Office.Tools.Word.Bookmark>ovládací prvky rozšíření nativní <xref:Microsoft.Office.Interop.Word.Bookmark> objekty povolením datové vazby a vystavení události. Další informace o hostitelských ovládacích prvcích najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
-   Nativní <xref:Microsoft.Office.Interop.Word.Bookmark> objektu.  
  
     <xref:Microsoft.Office.Interop.Word.Bookmark>objekty nemají vazby funkcí události nebo data.  
  
 Přiřadíte-li text na záložku, chování se liší <xref:Microsoft.Office.Interop.Word.Bookmark> a <xref:Microsoft.Office.Tools.Word.Bookmark>. Další informace najdete v tématu [ovládacího prvku záložek](../vsto/bookmark-control.md).  
  
## <a name="using-host-controls"></a>Použití ovládacích prvků hostitele  
  
#### <a name="to-update-bookmark-contents-using-a-bookmark-control"></a>Chcete-li aktualizovat obsah záložek pomocí ovládacího prvku záložek  
  
1.  Vytvoření procedury, která přebírá `bookmark` argument pro název záložky a `newText` argument řetězce přiřadit <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> vlastnost.  
  
    > [!NOTE]  
    >  Přiřazení text, který <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> nebo <xref:Microsoft.Office.Tools.Word.Bookmark.FormattedText%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Bookmark> řízení nezpůsobí záložku k odstranění.  
  
     [!code-vb[Trin_VstcoreWordAutomation#63](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#63)]
     [!code-csharp[Trin_VstcoreWordAutomation#63](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#63)]  
  
2.  Přiřadit *newText* řetězec, který <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     [!code-vb[Trin_VstcoreWordAutomation#64](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#64)]
     [!code-csharp[Trin_VstcoreWordAutomation#64](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#64)]  
  
## <a name="using-word-objects"></a>Použití objektů aplikace Word  
  
#### <a name="to-update-bookmark-contents-using-a-word-bookmark-object"></a>Aktualizovat obsah záložku pomocí objektu záložku aplikace Word  
  
1.  Vytvoření procedury, která má `bookmark` argument pro název <xref:Microsoft.Office.Interop.Word.Bookmark>a `newText` argument řetězce přiřadit <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost záložky.  
  
    > [!NOTE]  
    >  Přiřazení text do nativní aplikace Word <xref:Microsoft.Office.Interop.Word.Bookmark> objekt způsobí, že záložku k odstranění.  
  
     [!code-vb[Trin_VstcoreWordAutomation#65](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#65)]
     [!code-csharp[Trin_VstcoreWordAutomation#65](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#65)]  
  
2.  Přiřadit *newText* řetězec, který <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost záložky, kterou automaticky odstraní záložky. Znovu přidat záložku <xref:Microsoft.Office.Interop.Word.Bookmarks> kolekce.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#66)]
     [!code-csharp[Trin_VstcoreWordAutomation#66](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#66)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#66)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#66](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#66)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové vkládání textu do dokumentů aplikace Word](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Bookmark – ovládací prvek](../vsto/bookmark-control.md)  
  
  