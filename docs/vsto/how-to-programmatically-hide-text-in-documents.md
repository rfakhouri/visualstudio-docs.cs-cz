---
title: 'Postupy: Skrývání textu v dokumentech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], hiding text
- text [Office development in Visual Studio], hiding in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0c39a82a6b381296c47dcbf059b22e351dba3afc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646080"
---
# <a name="how-to-programmatically-hide-text-in-documents"></a>Postupy: Skrývání textu v dokumentech prostřednictvím kódu programu
  Text v dokumentu můžete skrýt nastavením <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Range.Font%2A> pro konkrétní rozsah textu.

 Například můžete dočasně skrýt text v rámci <xref:Microsoft.Office.Tools.Word.Bookmark> (v přizpůsobení úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Bookmark> (in VSTO Add-) před odesláním dokument na tiskárně.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-hide-text-in-a-bookmark-control-while-printing-the-document"></a>Chcete-li skrýt text v ovládacím prvku záložek při tisku dokumentu

1.  Vytvořte proceduru, která skrývá veškerý text, který je v zadaném rozsahu.

     [!code-vb[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#105)]
     [!code-csharp[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#105)]

2.  Vytvořte proceduru, která slouží k zobrazení veškerý text, který je v zadaném rozsahu.

     [!code-vb[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#106)]
     [!code-csharp[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#106)]

3.  Předat rozsah záložky `HideText` metoda, vytisknout dokument a pak předejte stejný rozsah na `UnhideText` metoda.

     Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu. Pokud chcete použít tento příklad, spusťte jej z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#107)]

     Následující příklad kódu je možné v doplňku VSTO. Tento příklad používá aktivní dokument. Pokud chcete použít v příkladu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#107)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad kódu předpokládá, že dokument obsahuje <xref:Microsoft.Office.Tools.Word.Bookmark> control (na úrovni dokumentu přizpůsobení) nebo <xref:Microsoft.Office.Interop.Word.Bookmark> ovládacího prvku (in VSTO Add-), který je pojmenován `bookmark1`.

## <a name="see-also"></a>Viz také:
- [Postupy: Tisk dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-print-documents.md)
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Programově resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [Postupy: Programově aktualizovat textu záložky](../vsto/how-to-programmatically-update-bookmark-text.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
