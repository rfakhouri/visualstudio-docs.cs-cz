---
title: 'Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, extending
- documents [Office development in Visual Studio], extending ranges
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 68c5e2811f437a01e171e33f9802503cf4d24922
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-extend-ranges-in-documents"></a>Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu
  Po definování <xref:Microsoft.Office.Interop.Word.Range> objekt v dokumentu aplikace Microsoft Office Word změnit jeho počáteční a koncové body pomocí <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> a <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metody. <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> a <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metody přijímají stejné dva argumenty, *jednotky* a *počet*. *Počet* argument je počet jednotek, které chcete přesunout a *jednotky* argument může mít jednu z následujících <xref:Microsoft.Office.Interop.Word.WdUnits> hodnoty:  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCharacter>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdWord>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSentence>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdParagraph>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSection>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdStory>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCell>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdColumn>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdRow>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdTable>  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 V následujícím příkladu definuje rozsah sedm znaků. Po původní počáteční pozice počáteční pozice rozsah sedm znaků, přesune se potom. Protože koncová pozice rozsahu byl také sedm znaků po počáteční pozice, výsledkem je, rozsah, který se skládá z nulový počet znaků. Kód pak se posouvá koncové znaky sedm pozice po aktuální koncová pozice.  
  
### <a name="to-extend-a-range"></a>K rozšíření rozsahu  
  
1.  Definujte rozsah znaků. Další informace najdete v tématu [postupy: definování prostřednictvím kódu programu a vyberte oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md).  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#39)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#39)]  
  
2.  Použití <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objekt, který chcete přesunout počáteční pozice rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#40)]
     [!code-csharp[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#40)]  
  
3.  Použití <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objekt, který chcete přesunout koncová pozice rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#41)]
     [!code-csharp[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#41)]  
  
## <a name="document-level-customization-code"></a>Kód přizpůsobení na úrovni dokumentu  
  
#### <a name="to-extend-a-range-in-a-document-level-customization"></a>Chcete-li rozšířit rozsah v přizpůsobení na úrovni dokumentu  
  
1.  Následující příklad ukazuje kód dokončení pro přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#38)]  
  
## <a name="vsto-add-in-code"></a>Kódu doplňku VSTO  
  
#### <a name="to-extend-a-range-in-an-application-level-vsto-add-in"></a>Chcete-li rozšířit rozsah v doplňku VSTO úrovni aplikace  
  
1.  Následující příklad ukazuje kód dokončení pro doplňku VSTO. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#38)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: dokumentů prostřednictvím kódu programu. resetování oblastí v aplikaci Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Postupy: programové sbalování oblastí nebo výběrů v dokumentech](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: načítání počátečních a koncových znaků v oblastech prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: Vyloučení značek odstavů při vytváření oblastí prostřednictvím kódu programu](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  