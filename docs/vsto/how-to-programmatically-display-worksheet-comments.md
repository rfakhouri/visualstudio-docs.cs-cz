---
title: 'Postupy: Zobrazování komentářů v listech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 117643390f5c6bd9e62ec0ee8c8d58c28ec4e1b8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602241"
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Postupy: Zobrazování komentářů v listech prostřednictvím kódu programu
  Můžete programově zobrazení a skrytí komentářů v listech aplikace Microsoft Office Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Chcete-li zobrazit všechny komentáře na listu v přizpůsobení na úrovni dokumentu

1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete, aby zobrazovaly komentáře; v opačném případě **false**. Tento kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.

     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]

## <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Chcete-li zobrazit všechny komentáře na listu v doplňku VSTO úrovni aplikace

1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete, aby zobrazovaly komentáře; v opačném případě **false**.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: Programové přidávání a odstraňování komentářů v listech](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
