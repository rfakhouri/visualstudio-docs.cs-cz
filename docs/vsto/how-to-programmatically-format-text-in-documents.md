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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 602c9e8f3e846f38a50c39c34f5d08f47f74d155
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
 [Postupy: Hledání a nahrazování textu v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)  
  
  