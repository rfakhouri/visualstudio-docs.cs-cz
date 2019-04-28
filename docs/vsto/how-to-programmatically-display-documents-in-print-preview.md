---
title: 'Postupy: Zobrazování dokumentů v náhledu prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], displaying documents in print preview
- documents [Office development in Visual Studio], displaying in print preview
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d8296d28e884c746e09b427914af02213bbbaa7e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62813033"
---
# <a name="how-to-programmatically-display-documents-in-print-preview"></a>Postupy: Zobrazování dokumentů v náhledu prostřednictvím kódu programu
  Pokud vaše řešení generuje sestavu, můžete chtít zobrazit sestavy pro uživatele v režimu náhledu.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="procedures-for-document-level-customizations"></a>Postupy pro přizpůsobení na úrovni dokumentu

### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>K zobrazení dokumentu v náhledu voláním printpreview – metoda

1. Volání <xref:Microsoft.Office.Tools.Word.Document.PrintPreview%2A> metodu <xref:Microsoft.Office.Tools.Word.Document> třídy. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#13)]

### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>K zobrazení dokumentu v náhledu tak, že nastavíte printpreview – vlastnost

1. Nastavte <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Application> objektu **true**.

     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]

## <a name="procedures-for-vsto-add-ins"></a>Postupy pro doplňky VSTO

### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>K zobrazení dokumentu v náhledu voláním printpreview – metoda

1. Volání <xref:Microsoft.Office.Interop.Word._Document.PrintPreview%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> , který chcete ve verzi preview. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#13)]

### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>K zobrazení dokumentu v náhledu tak, že nastavíte printpreview – vlastnost

1. Nastavte <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Application> objektu **true**.

     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]

## <a name="see-also"></a>Viz také:
- [Postupy: Tisk dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-print-documents.md)
- [Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)
- [Postupy: Vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)
