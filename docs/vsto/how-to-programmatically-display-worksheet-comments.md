---
title: "Postupy: zobrazování komentářů v listech prostřednictvím kódu programu | Microsoft Docs"
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
- worksheets, comments
- comments, worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c43e33030cffc78bc8ee4a0665c9334bc6e8bca7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Postupy: Zobrazování komentářů v listech prostřednictvím kódu programu
  Lze programově zobrazit nebo skrýt komentářů v listech aplikace Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Chcete-li zobrazit všechny komentáře na list v přizpůsobení na úrovni dokumentu  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete zobrazit komentáře; jinak **false**. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Chcete-li zobrazit všechny komentáře na list v doplňku VSTO úrovni aplikace  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete zobrazit komentáře; jinak **false**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Programové přidávání a odstraňování komentářů v listech](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  