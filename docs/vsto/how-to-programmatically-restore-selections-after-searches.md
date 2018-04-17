---
title: 'Postupy: programové obnovení výběru po hledání | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- searches, restoring selection after
- documents [Office development in Visual Studio], restoring selections
- selections, restoring after a search
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7d1f4181a1ce9431ecbdb69a4b4f00a70f8259d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-restore-selections-after-searches"></a>Postupy: Obnovení výběru po hledání prostřednictvím kódu programu
  Pokud najít a nahradit text v dokumentu, můžete obnovit původní výběr uživatele po dokončení hledání.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 V postupu ukázkový kód využívá dva <xref:Microsoft.Office.Interop.Word.Range> objekty. Jeden uloží aktuální <xref:Microsoft.Office.Interop.Word.Selection>, a jeden nastaví celý dokument, který chcete použít jako rozsah vyhledávání.  
  
### <a name="to-restore-the-users-original-selection-after-a-search"></a>Chcete-li obnovit původní výběr uživatele po hledání  
  
1.  Vytvořte <xref:Microsoft.Office.Interop.Word.Range> objekty pro aktuální výběr a dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#83)]
     [!code-csharp[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#83)]  
  
2.  Provést hledání a nahrazení operaci.  
  
     [!code-vb[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#84)]
     [!code-csharp[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#84)]  
  
3.  Vyberte počáteční oblast, kterou chcete obnovit původní výběr uživatele.  
  
     [!code-vb[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#85)]
     [!code-csharp[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#85)]  
  
 Následující příklad ukazuje metodu dokončení.  
  
## <a name="example"></a>Příklad  
 [!code-vb[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#82)]
 [!code-csharp[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#82)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: hledání prostřednictvím kódu programu a nahrazení textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Postupy: nastavování možností hledání v aplikaci Word](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Postupy: procházení nalezených položek v dokumentech prostřednictvím kódu programu cykly](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  