---
title: 'Postupy: Programově počet znaků v dokumentech'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- characters, counting in documents
- counting characters in documents
- documents [Office development in Visual Studio], counting characters
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fb4bbb124575346c930fa5539801deb3c9981cac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575241"
---
# <a name="how-to-programmatically-count-characters-in-documents"></a>Postupy: Programově počet znaků v dokumentech
  Na pozici znaku 0, který reprezentuje bod vložení je první znak v dokumentu. Poslední pozice znaku rovná celkový počet znaků v dokumentu. Můžete určit počet znaků v dokumentu s použitím <xref:Microsoft.Office.Interop.Word.Characters.Count%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Characters> kolekce.

 Počítají se všechny znaky v dokumentu, včetně mezer, značek odstavů a dalších znaků, které jsou obvykle skryta. Ještě nový prázdný dokument vrací počet jeden znak, protože obsahuje značku odstavce.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-display-the-number-of-characters-in-a-document-level-customization"></a>Chcete-li zobrazit počet znaků v přizpůsobení na úrovni dokumentu

1. Vybere celý dokument.

     [!code-vb[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#98)]

2. Zobrazte počet znaků v dokumentu v okně se zprávou.

     [!code-vb[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#99)]

## <a name="to-display-the-number-of-characters-in-a-vsto-add-in"></a>Chcete-li zobrazit počet znaků v doplňku VSTO

1. Vybere celý dokument. V následujícím příkladu vybere aktivní dokument.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#98)]

2. Zobrazte počet znaků v dokumentu v okně se zprávou.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#99)]

## <a name="see-also"></a>Viz také:
- [Postupy: Načítání počátečních a koncových znaků oblastí prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
