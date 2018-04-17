---
title: 'Postupy: tisk dokumentů prostřednictvím kódu programu | Microsoft Docs'
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
ms.openlocfilehash: 1a5364bd2cf0f0ea6d5e7ceb7c8a427c5aea301d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-print-documents"></a>Postupy: Tisk dokumentů prostřednictvím kódu programu
  Můžete si ho vytisknout celou dokument aplikace Microsoft Office Word či součástí dokument, výchozí tiskárny.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="printing-a-document-that-is-part-of-a-document-level-customization"></a>Tisk dokumentu, který je součástí přizpůsobení na úrovni dokumentu  
  
#### <a name="to-print-the-entire-document"></a>Tisknout celý dokument.  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídy ve vašem projektu a tisknout celý dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#11)]  
  
#### <a name="to-print-the-current-page-of-the-document"></a>Tisk aktuální stránky z dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídy ve vašem projektu a určit, že jedna kopie aktuální stránky vytištěn. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` třídy.  
  
     [!code-vb[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#12)]  
  
## <a name="printing-a-document-by-using-an-vsto-add-in"></a>Tisk dokumentu pomocí doplňku VSTO  
  
#### <a name="to-print-an-entire-document"></a>Tisknout celý dokument.  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout. Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#11)]  
  
#### <a name="to-print-the-current-page-of-a-document"></a>Tisk aktuální stránky dokumentu  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout a určit, že jedna kopie aktuální stránky vytištěn. Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#12)]  
  
## <a name="see-also"></a>Viz také  
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  