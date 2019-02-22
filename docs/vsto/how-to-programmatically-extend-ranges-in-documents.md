---
title: 'Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, extending
- documents [Office development in Visual Studio], extending ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 13aca5195a965fb6078be80e5fe681a49e7d4a09
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56639257"
---
# <a name="how-to-programmatically-extend-ranges-in-documents"></a>Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu
  Po definování <xref:Microsoft.Office.Interop.Word.Range> objektu v dokumentu aplikace Microsoft Office Word změnit jeho počátečního a koncového bodu pomocí <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> a <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metody. <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> a <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metody přijímají dva stejné argumenty *jednotky* a *počet*. *Počet* argument je počet jednotek, které chcete přesunout a *jednotky* argument může být jeden z následujících <xref:Microsoft.Office.Interop.Word.WdUnits> hodnoty:

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdCharacter>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdWord>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdSentence>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdParagraph>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdSection>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdStory>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdCell>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdColumn>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdRow>

- <xref:Microsoft.Office.Interop.Word.WdUnits.wdTable>

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

  Následující příklad definuje rozsah sedm znaků. Po původní počáteční pozice počáteční pozici rozsah sedm znaků, přesune se potom. Protože koncová pozice rozsahu byl také 7 znaků po počáteční pozice, výsledkem je rozsah, který se skládá z žádného znaku. Kód převezme, změní koncové pozici sedm znaky za aktuální pozicí end.

## <a name="to-extend-a-range"></a>Chcete-li rozšířit rozsah

1.  Definujte rozsah znaků. Další informace najdete v tématu [jak: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md).

     Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu.

     [!code-vb[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#39)]

     Následující příklad kódu je možné v doplňku VSTO. Tento příklad používá aktivní dokument.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#39)]

2.  Použití <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objektu přesunout počáteční pozice v rozsahu.

     [!code-vb[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#40)]
     [!code-csharp[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#40)]

3.  Použití <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objektu přesunout koncová pozice rozsahu.

     [!code-vb[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#41)]
     [!code-csharp[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#41)]

## <a name="document-level-customization-code"></a>Kód přizpůsobení na úrovni dokumentu

### <a name="to-extend-a-range-in-a-document-level-customization"></a>Chcete-li rozšířit rozsah v přizpůsobení na úrovni dokumentu

1.  Následující příklad ukazuje kompletní kód pro přizpůsobení na úrovni dokumentu. Chcete-li tento kód použít, spusťte z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#38)]

## <a name="vsto-add-in-code"></a>Kód doplňku VSTO

### <a name="to-extend-a-range-in-an-application-level-vsto-add-in"></a>Chcete-li rozšířit rozsah v doplňku VSTO úrovni aplikace

1.  Následující příklad ukazuje kompletní kód doplňku VSTO. Chcete-li tento kód použít, spusťte z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#38)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [Postupy: Oblastí nebo výběrů v dokumentech prostřednictvím kódu programu sbalit](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)
- [Postupy: Programově vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)
