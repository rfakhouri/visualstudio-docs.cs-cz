---
title: "Postupy: programové sbalování oblastí nebo výběrů v dokumentech | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- selections, collapsing
- documents [Office development in Visual Studio], collapsing ranges
- collapsing selections
- ranges, collapsing
- collapsing ranges
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c3d3c4d81f8da08e90d7d5588ecaed8e548824a5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-collapse-ranges-or-selections-in-documents"></a>Postupy: Sbalování oblastí nebo výběrů v dokumentech prostřednictvím kódu programu
  Pokud pracujete <xref:Microsoft.Office.Interop.Word.Range> nebo <xref:Microsoft.Office.Interop.Word.Selection> objekt, můžete chtít změnit výběr na bod vložení před vkládání textu, aby nedošlo k přepsání existujícího textu. Jak <xref:Microsoft.Office.Interop.Word.Range> a <xref:Microsoft.Office.Interop.Word.Selection> objekty mají sbalit metoda, která využívá <xref:Microsoft.Office.Interop.Word.WdCollapseDirection> hodnot výčtu:  
  
-   <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart>Sbalí výběru na začátek výběru. Toto je výchozí, pokud nezadáte hodnotu výčtu.  
  
-   <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd>Sbalí výběru na konec výběru.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-collapse-a-range-and-insert-new-text"></a>Sbalit rozsah a zadejte nový text  
  
1.  Vytvoření <xref:Microsoft.Office.Interop.Word.Range> objekt, který se skládá z první odstavce do dokumentu.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#46)]
     [!code-csharp[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#46)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento kód používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#46)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#46)]  
  
2.  Použití <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart> hodnota výčtu sbalit rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#47)]
     [!code-csharp[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#47)]  
  
3.  Vložte nového textu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#48)]
     [!code-csharp[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#48)]  
  
4.  Vyberte <xref:Microsoft.Office.Interop.Word.Range>.  
  
     [!code-vb[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#49)]
     [!code-csharp[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#49)]  
  
 Pokud použijete <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd> hodnota výčtu, text je vložen na začátku odstavec.  
  
 [!code-vb[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#50)]
 [!code-csharp[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#50)]  
  
 Můžou očekávat, že vkládání nové věty by vloží ho před značku odstavce, ale který je tak není, protože původní rozsah obsahuje značku odstavce. Další informace najdete v tématu [postupy: programové vyloučit odstavce značky při vytváření rozsahy](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md).  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
#### <a name="to-collapse-a-range-in-a-document-level-customization"></a>Chcete-li sbalit oblast v přizpůsobení na úrovni dokumentu  
  
1.  Následující příklad ukazuje metodu dokončení pro přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#45)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
#### <a name="to-collapse-a-range-in-an-vsto-add-in"></a>Chcete-li sbalit oblast v doplňku VSTO  
  
1.  Následující příklad ukazuje metodu dokončení pro doplňku VSTO. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#45)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové vkládání textu do dokumentů aplikace Word](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: načítání počátečních a koncových znaků v oblastech prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: programové vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: Resetování oblastí v dokumentech aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)  
  