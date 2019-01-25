---
title: 'Postupy: Oblastí nebo výběrů v dokumentech prostřednictvím kódu programu sbalit'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- selections, collapsing
- documents [Office development in Visual Studio], collapsing ranges
- collapsing selections
- ranges, collapsing
- collapsing ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 40dbfca783b75657ba820bdd03695a326bec3343
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864641"
---
# <a name="how-to-programmatically-collapse-ranges-or-selections-in-documents"></a>Postupy: Oblastí nebo výběrů v dokumentech prostřednictvím kódu programu sbalit
  Pokud pracujete <xref:Microsoft.Office.Interop.Word.Range> nebo <xref:Microsoft.Office.Interop.Word.Selection> objektu, můžete chtít změnit výběr na bod vložení před vložení textu, aby nedošlo k přepsání existující text. Jak <xref:Microsoft.Office.Interop.Word.Range> a <xref:Microsoft.Office.Interop.Word.Selection> objekty mají sbalit metodu, která využívá <xref:Microsoft.Office.Interop.Word.WdCollapseDirection> hodnot výčtu:  
  
- <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart> Sbalí výběr na začátek výběru. Toto je výchozí, pokud nezadáte hodnotu výčtu.  
  
- <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd> Sbalí výběr do zakončení výběru.  
  
  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-collapse-a-range-and-insert-new-text"></a>Sbalit oblast a vložit nový text  
  
1. Vytvoření <xref:Microsoft.Office.Interop.Word.Range> objekt, který se skládá z prvního odstavce v dokumentu.  
  
    Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu.  
  
    [!code-vb[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#46)]
    [!code-csharp[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#46)]  
  
    Následující příklad kódu je možné v doplňku VSTO. Tento kód používá aktivního dokumentu.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#46)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#46)]  
  
2. Použití <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart> hodnotu výčtu pro sbalení rozsahu.  
  
    [!code-vb[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#47)]
    [!code-csharp[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#47)]  
  
3. Vložte nový text.  
  
    [!code-vb[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#48)]
    [!code-csharp[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#48)]  
  
4. Vyberte <xref:Microsoft.Office.Interop.Word.Range>.  
  
    [!code-vb[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#49)]
    [!code-csharp[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#49)]  
  
   Pokud používáte <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd> hodnotu výčtu, text se vloží na začátek odstavec.  
  
   [!code-vb[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#50)]
   [!code-csharp[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#50)]  
  
   Očekáváte, že vložení nového větu by jej vložit před značku odstavce, ale to je tomu tak není, protože původní rozsah obsahuje značku odstavce. Další informace najdete v tématu [jak: Při vytváření oblastí prostřednictvím kódu programu vyloučení značek odstavů](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md).  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="to-collapse-a-range-in-a-document-level-customization"></a>Chcete-li sbalit oblast v přizpůsobení na úrovni dokumentu  
  
1.  Následující příklad ukazuje kompletní metodu pro přizpůsobení na úrovni dokumentu. Chcete-li tento kód použít, spusťte z `ThisDocument` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#45)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="to-collapse-a-range-in-a-vsto-add-in"></a>Chcete-li sbalit oblast v doplňku VSTO  
  
1.  Následující příklad ukazuje kompletní metodu pro doplňku VSTO. Chcete-li tento kód použít, spusťte z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#45)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Vkládání textu do dokumentů aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: Programově vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: Programově resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)  
