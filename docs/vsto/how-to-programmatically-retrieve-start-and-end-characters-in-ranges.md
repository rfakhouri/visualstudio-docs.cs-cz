---
title: 'Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 041693d5d81fb13e812b260171ec95a2bd183a6a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955664"
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu
  Tento příklad ukazuje, jak můžete načíst pozice znaku pozic začátek a konec rozsahu.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>K načtení počátečních a koncových znaků rozsahu v přizpůsobení na úrovni dokumentu

1. Získat hodnoty <xref:Microsoft.Office.Interop.Word.Range.Start%2A> a <xref:Microsoft.Office.Interop.Word.Range.End%2A> vlastnosti <xref:Microsoft.Office.Interop.Word.Range> objektu. Následující příklad kódu získá počáteční a koncovou pozici druhého větu v dokumentu. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]

## <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-a-vsto-add-in"></a>K načtení počátečních a koncových znaků rozsahu pomocí doplňku VSTO

1. Získat hodnoty <xref:Microsoft.Office.Interop.Word.Range.Start%2A> a <xref:Microsoft.Office.Interop.Word.Range.End%2A> vlastnosti <xref:Microsoft.Office.Interop.Word.Range> objektu. Následující příklad kódu získá počáteční a koncovou pozici druhého větu v aktivním dokumentu. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [Postupy: Programově resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)
- [Postupy: Oblastí nebo výběrů v dokumentech prostřednictvím kódu programu sbalit](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)
- [Postupy: Programově vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)
- [Postupy: Programově počet znaků v dokumentech](../vsto/how-to-programmatically-count-characters-in-documents.md)
