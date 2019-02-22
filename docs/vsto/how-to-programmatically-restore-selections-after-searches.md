---
title: 'Postupy: Obnovení výběru po hledání prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- searches, restoring selection after
- documents [Office development in Visual Studio], restoring selections
- selections, restoring after a search
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 672c66fef5d7400601ce69270b5cd4f525b34c7d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607899"
---
# <a name="how-to-programmatically-restore-selections-after-searches"></a>Postupy: Obnovení výběru po hledání prostřednictvím kódu programu
  Je-li najít a nahradit text v dokumentu, můžete chtít obnovit původní výběru uživatele po dokončení hledání.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Kód v postupu Ukázka používá dva <xref:Microsoft.Office.Interop.Word.Range> objekty. Jeden ukládá aktuální <xref:Microsoft.Office.Interop.Word.Selection>, a jeden nastaví celý dokument určený jako rozsah hledání.

## <a name="to-restore-the-users-original-selection-after-a-search"></a>Chcete-li obnovit uživatele původního výběru po hledání

1. Vytvořte <xref:Microsoft.Office.Interop.Word.Range> objekty pro dokument a aktuálního výběru.

    [!code-vb[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#83)]
    [!code-csharp[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#83)]

2. Provést hledání a nahrazení operace.

    [!code-vb[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#84)]
    [!code-csharp[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#84)]

3. Vyberte začátek rozsahu, chcete-li obnovit původní výběru uživatele.

    [!code-vb[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#85)]
    [!code-csharp[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#85)]

   Následující příklad ukazuje kompletní metodu.

## <a name="example"></a>Příklad
 [!code-vb[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#82)]
 [!code-csharp[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#82)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově hledání a nahrazování textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Postupy: Nastavování možností hledání v aplikaci Word](../vsto/how-to-programmatically-set-search-options-in-word.md)
- [Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu smyčky](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
