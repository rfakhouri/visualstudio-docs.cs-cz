---
title: 'Postupy: zobrazování dokumentů v náhledu tisku prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], displaying documents in print preview
- documents [Office development in Visual Studio], displaying in print preview
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bca26eb30ed9c468d154dbba6e2f126d3c61050f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-display-documents-in-print-preview"></a>Postupy: Zobrazování dokumentů v náhledu tisku prostřednictvím kódu programu
  Pokud vaše řešení generuje sestavy, můžete chtít zobrazit sestavy pro uživatele v režimu náhledu tisku.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="procedures-for-document-level-customizations"></a>Postupy pro úpravy na úrovni dokumentů  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>Zobrazení dokumentu v náhledu voláním printpreview – metoda  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintPreview%2A> metodu <xref:Microsoft.Office.Tools.Word.Document> třídy. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>Zobrazení dokumentu v náhledu nastavením printpreview – vlastnost  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Application> do objektu **true**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="procedures-for-vsto-add-ins"></a>Postupy pro doplňky VSTO  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>Zobrazení dokumentu v náhledu voláním printpreview – metoda  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintPreview%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> , kterou chcete zobrazit náhled. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>Zobrazení dokumentu v náhledu nastavením printpreview – vlastnost  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Application> do objektu **true**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: tisk dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-print-documents.md)   
 [Postupy: otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Postupy: Vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)  
  
  