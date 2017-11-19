---
title: "Postupy: skrývání textu v dokumentech prostřednictvím kódu programu | Microsoft Docs"
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
- documents [Office development in Visual Studio], hiding text
- text [Office development in Visual Studio], hiding in documents
ms.assetid: f5ced4ec-22ca-463b-b963-d34ce631b486
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b9ec425a3d83ea088e47725866688ada834ffd34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-hide-text-in-documents"></a>Postupy: Skrývání textu v dokumentech prostřednictvím kódu programu
  Text v dokumentu můžete skrýt, a to nastavením <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Range.Font%2A> pro konkrétní rozsah textu.  
  
 Například můžete dočasně skrýt textu v rámci <xref:Microsoft.Office.Tools.Word.Bookmark> (v přizpůsobení na úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Bookmark> (v VSTO doplňku) před odesláním dokumentu na tiskárně.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-hide-text-in-a-bookmark-control-while-printing-the-document"></a>Chcete-li skrýt textu v ovládacím prvku záložek při tisku dokumentu  
  
1.  Vytvoření procedury, která skryje celý text, který je v zadaném rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#105)]
     [!code-csharp[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#105)]  
  
2.  Vytvoření procedury, která slouží k zobrazení všech text, který je v zadaném rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#106)]
     [!code-csharp[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#106)]  
  
3.  Předat rozsahu záložku `HideText` metody tisk dokumentu a poté předat do stejného rozsahu `UnhideText` metoda.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#107)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument. Pokud chcete použít v příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#107)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu předpokládá, že obsahuje dokument <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku (přizpůsobení na úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Bookmark> ovládacího prvku (VSTO doplňku) s názvem `bookmark1`.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: tisk dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-print-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: dokumentů prostřednictvím kódu programu. resetování oblastí v aplikaci Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Postupy: aktualizace textu záložek prostřednictvím kódu programu](../vsto/how-to-programmatically-update-bookmark-text.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  