---
title: 'Postupy: Programově formátování textu v dokumentech'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formatting [Office development in Visual Studio]
- documents [Office development in Visual Studio], formatting text
- text [Office development in Visual Studio], formatting in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ba0c69768f8961fa6c23a599a385c46a93d7c47c
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875391"
---
# <a name="how-to-programmatically-format-text-in-documents"></a>Postupy: Programově formátování textu v dokumentech
  Můžete použít <xref:Microsoft.Office.Interop.Word.Range> objekt pro formátování textu v dokumentu aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 V následujícím příkladu vybere první odstavec v dokumentu a změní velikost písma a název písma, zarovnání. Potom vybere rozsah a zobrazí okno se zprávou k pozastavení před provedením další části kódu. V další části volá metodu zpět <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt (pro přizpůsobení na úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Document> třídy (pro doplňku VSTO) třikrát. Použije styl odsazení normální a zobrazí okno se zprávou pozastavit kód. Potom kód volá <xref:Microsoft.Office.Tools.Word.Document.Undo%2A> metoda jednou a zobrazí okno se zprávou.  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="to-format-text-using-a-document-level-customization"></a>K formátování textu s použitím přizpůsobení úrovni dokumentu  
  
1.  Následující příklad je možné v přizpůsobení na úrovni dokumentu. Chcete-li tento kód použít, spusťte z `ThisDocument` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#62)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="to-format-text-using-a-vsto-add-in"></a>K formátování textu pomocí doplňku VSTO  
  
1.  Následující příklad je možné v doplňku VSTO. Tento příklad používá aktivní dokument. Chcete-li tento kód použít, spusťte z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#62)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: Vkládání textu do dokumentů aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Postupy: Programově hledání a nahrazování textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)  
