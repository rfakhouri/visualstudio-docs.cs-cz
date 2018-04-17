---
title: 'Postupy: dokumentů prostřednictvím kódu programu. resetování oblastí v aplikaci Word | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], resetting ranges
- ranges, resetting in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ed267f4ed2211f2dda69b620aec9fdadbe5a76c2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-reset-ranges-in-word-documents"></a>Postupy: Resetování oblastí v dokumentech aplikace Word prostřednictvím kódu programu
  Použití <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> metoda ke změně velikosti stávající rozsah v dokumentu aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-reset-an-existing-range"></a>Chcete-li obnovit existující rozsahu  
  
1.  Nastavte počáteční rozsah od prvních sedm znaků v dokumentu.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#43)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento kód používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#43)]  
  
2.  Použití <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> počáteční rozsah v druhé větě a končit na konci páté věty.  
  
     [!code-vb[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#44)]
     [!code-csharp[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#44)]  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
#### <a name="to-reset-an-existing-range-in-a-document-level-customization"></a>Chcete-li obnovit stávající rozsah v přizpůsobení na úrovni dokumentu  
  
1.  Následující příklad ukazuje na kompletní příklad přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#42)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
#### <a name="to-reset-an-existing-range-in-an-vsto-add-in"></a>Chcete-li obnovit stávající rozsah v doplňku VSTO  
  
1.  Následující příklad ukazuje kompletní příklad pro doplňku VSTO. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#42)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: načítání počátečních a koncových znaků v oblastech prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: Sbalování oblastí nebo výběrů v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)  
  
  