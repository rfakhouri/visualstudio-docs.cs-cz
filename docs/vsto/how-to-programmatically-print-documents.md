---
title: 'Postupy: tisk dokumentů prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], printing documents
- documents [Office development in Visual Studio], printing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c43380a9fe3cfdb2bf6de24648e2be1cde064dae
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258028"
---
# <a name="how-to-programmatically-print-documents"></a>Postupy: tisk dokumentů prostřednictvím kódu programu
  Můžete si ho vytisknout celou dokument aplikace Microsoft Office Word či součástí dokument, výchozí tiskárny.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="print-a-document-that-is-part-of-a-document-level-customization"></a>Tisk dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
### <a name="to-print-the-entire-document"></a>Tisknout celý dokument.  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídy ve vašem projektu a tisknout celý dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#11)]  
  
### <a name="to-print-the-current-page-of-the-document"></a>Tisk aktuální stránky z dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídy ve vašem projektu a určit, že jedna kopie aktuální stránky vytištěn. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#12)]  
  
## <a name="print-a-document-by-using-an-vsto-add-in"></a>Tisk dokumentu pomocí doplňku VSTO  
  
### <a name="to-print-an-entire-document"></a>Tisknout celý dokument.  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout. Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#11)]  
  
### <a name="to-print-the-current-page-of-a-document"></a>Tisk aktuální stránky dokumentu  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout a určit, že jedna kopie aktuální stránky vytištěn. Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#12)]  
  
## <a name="see-also"></a>Viz také:  
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  