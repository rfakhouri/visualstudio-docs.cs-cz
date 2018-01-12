---
title: "Postupy: procházení nalezených položek v dokumentech prostřednictvím kódu programu cykly | Microsoft Docs"
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
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7ad153a0a08546ebc9fad93ce7287e4c2fc4a043
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Word.Find> Třída má <xref:Microsoft.Office.Interop.Word.Find.Found%2A> vlastnost, která vrací **true** vždy, když je položka hledané nalezena. Můžete projít všechny instance, které jsou součástí <xref:Microsoft.Office.Interop.Word.Range> pomocí <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metoda.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-loop-through-found-items"></a>K procházení nalezených položek  
  
1.  Deklarace <xref:Microsoft.Office.Interop.Word.Range> objektu.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]  
  
2.  Použití <xref:Microsoft.Office.Interop.Word.Find.Found%2A> vlastnost ve smyčce a vyhledejte všechny výskyty řetězce v dokumentu a zvýšit proměnná s celým číslem o 1 pokaždé, když je nalezen řetězec.  
  
     [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
     [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]  
  
3.  Zobrazí počet řetězce byl nalezen v okně se zprávou.  
  
     [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
     [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]  
  
 Následující příklady ukazují metodu dokončení.  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
#### <a name="to-loop-through-items-in-a-document-level-customization"></a>Můžete procházet položky v přizpůsobení na úrovni dokumentu  
  
1.  Následující příklad ukazuje kód dokončení pro přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
#### <a name="to-loop-through-items-in-an-vsto-add-in"></a>Můžete procházet položky v doplňku VSTO  
  
1.  Následující příklad ukazuje kód dokončení pro doplňku VSTO. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: hledání prostřednictvím kódu programu a nahrazení textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Postupy: nastavování možností hledání v aplikaci Word](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: programové obnovení výběru po hledání](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  