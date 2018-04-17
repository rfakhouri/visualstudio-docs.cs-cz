---
title: 'Postupy: Programové načítání počátečních a koncových znaků oblastí | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a79112e80885dfd64b85a90125ea059277725d33
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>Postup: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu
  Tento příklad ukazuje, jak můžete načíst znak pozice počáteční a koncové pozice rozsahu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>K načtení počátečních a koncových znaků rozsahu v přizpůsobení na úrovni dokumentu  
  
1.  Získat hodnoty <xref:Microsoft.Office.Interop.Word.Range.Start%2A> a <xref:Microsoft.Office.Interop.Word.Range.End%2A> vlastnosti <xref:Microsoft.Office.Interop.Word.Range> objektu. Následující příklad kódu získá počáteční a koncovou pozici druhého věty v dokumentu. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-an-vsto-add-in"></a>Načtení počátečních a koncových znaků rozsahu pomocí doplňku VSTO  
  
1.  Získat hodnoty <xref:Microsoft.Office.Interop.Word.Range.Start%2A> a <xref:Microsoft.Office.Interop.Word.Range.End%2A> vlastnosti <xref:Microsoft.Office.Interop.Word.Range> objektu. Následující příklad kódu získá počáteční a koncovou pozici druhého větu v aktivním dokumentu. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: dokumentů prostřednictvím kódu programu. resetování oblastí v aplikaci Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Postupy: programové sbalování oblastí nebo výběrů v dokumentech](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Postupy: programové vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Postupy: Počítání znaků v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-count-characters-in-documents.md)  
  
  