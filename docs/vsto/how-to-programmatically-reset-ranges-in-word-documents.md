---
title: 'Postupy: Programově resetování oblastí v dokumentech aplikace Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], resetting ranges
- ranges, resetting in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8643f7d10593ee2bcf51245d05edcd153db6b19d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56609810"
---
# <a name="how-to-programmatically-reset-ranges-in-word-documents"></a>Postupy: Programově resetování oblastí v dokumentech aplikace Word
  Použití <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> metody pro změnu velikosti existujícího oblast v dokumentu aplikace Microsoft Office Word.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-reset-an-existing-range"></a>Chcete-li obnovit stávající rozsah

1.  Nastavte jako počáteční rozsah od prvních 7 znaků v dokumentu.

     Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu.

     [!code-vb[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#43)]

     Následující příklad kódu je možné v doplňku VSTO. Tento kód používá aktivního dokumentu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#43)]

2.  Použití <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> počáteční rozsah v druhé věty a končí na konci páté věty.

     [!code-vb[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#44)]
     [!code-csharp[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#44)]

## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu

### <a name="to-reset-an-existing-range-in-a-document-level-customization"></a>Chcete-li obnovit stávající rozsah v přizpůsobení na úrovni dokumentu

1.  Následující příklad ukazuje kompletní příklad pro přizpůsobení na úrovni dokumentu. Chcete-li tento kód použít, spusťte z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#42)]

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="to-reset-an-existing-range-in-a-vsto-add-in"></a>Chcete-li obnovit stávající rozsah v doplňku VSTO

1.  Následující příklad ukazuje kompletní příklad pro doplňku VSTO. Chcete-li tento kód použít, spusťte z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#42)]

## <a name="see-also"></a>Viz také:
- [Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)
- [Postupy: Oblastí nebo výběrů v dokumentech prostřednictvím kódu programu sbalit](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
