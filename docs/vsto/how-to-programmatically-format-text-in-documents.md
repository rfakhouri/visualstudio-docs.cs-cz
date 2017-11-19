---
title: "Postupy: formátování textu v dokumentech prostřednictvím kódu programu | Microsoft Docs"
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
- formatting [Office development in Visual Studio]
- documents [Office development in Visual Studio], formatting text
- text [Office development in Visual Studio], formatting in documents
ms.assetid: 0a84893b-5ccc-4515-a2dc-95773ee8eaba
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d35416b529214dd4c2dc89f3b8de3fb8eeab9f5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-format-text-in-documents"></a>Postupy: Formátování textu v dokumentech prostřednictvím kódu programu
  Můžete použít <xref:Microsoft.Office.Interop.Word.Range> objekt do formátu textu v dokumentu aplikace Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 V následujícím příkladu se vybere první odstavce do dokumentu a změní velikost písma, název písma a zarovnání. Potom vybere rozsahu a zobrazí okno se zprávou pozastavit před provedením další části kódu. V další části volá metodu vrácení zpět <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka (pro přizpůsobení na úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Document> třídy (pro modul Add-in VSTO) třikrát. Ji používá styl Normální odsazení a zobrazí okno se zprávou pozastavit kód. Potom kód zavolá metodu <xref:Microsoft.Office.Tools.Word.Document.Undo%2A> metoda jednou a zobrazí se okno se zprávou.  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
#### <a name="to-format-text-using-a-document-level-customization"></a>K formátování textu s použitím přizpůsobení na úrovni dokumentu  
  
1.  V následujícím příkladu lze použít v přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#62)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
#### <a name="to-format-text-using-a-vsto-add-in"></a>K formátování textu s použitím doplňku VSTO  
  
1.  V následujícím příkladu lze v doplňku VSTO. Tento příklad používá aktivní dokument. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#62)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#62](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#62)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: programové vkládání textu do dokumentů aplikace Word](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Postupy: hledání prostřednictvím kódu programu a nahrazení textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)  
  
  