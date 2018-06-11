---
title: 'Postupy: programové počet znaků v dokumentech'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- characters, counting in documents
- counting characters in documents
- documents [Office development in Visual Studio], counting characters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d74a44b57a4d51690af3cadda62b8849a55363e0
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256354"
---
# <a name="how-to-programmatically-count-characters-in-documents"></a>Postupy: programové počet znaků v dokumentech
  První znak v dokumentu je na pozici znaku 0, který reprezentuje bod vložení. Poslední pozice znaku rovná celkový počet znaků v dokumentu. Můžete určit počet znaků v dokumentu s použitím <xref:Microsoft.Office.Interop.Word.Characters.Count%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Characters> kolekce.  
  
 Počítají se všechny znaky v dokumentu, včetně prostorů, značky odstavce a dalšími znaky, které jsou obvykle skryta. I nového prázdného dokumentu vrací počet jeden znak, protože obsahuje značku odstavce.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-display-the-number-of-characters-in-a-document-level-customization"></a>Chcete-li zobrazit počet znaků v přizpůsobení na úrovni dokumentu  
  
1.  Vybere celý dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#98)]  
  
2.  Zobrazí počet znaků v dokumentu v okně se zprávou.  
  
     [!code-vb[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#99)]  
  
## <a name="to-display-the-number-of-characters-in-an-vsto-add-in"></a>Chcete-li zobrazit počet znaků v doplňku VSTO  
  
1.  Vybere celý dokument. Následující příklad vybere aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#98)]  
  
2.  Zobrazí počet znaků v dokumentu v okně se zprávou.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#99)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: načítání počátečních a koncových znaků v oblastech prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)  
  
  