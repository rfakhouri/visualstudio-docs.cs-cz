---
title: "Postupy: programové přidání záhlaví a zápatí do dokumentů | Microsoft Docs"
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
- headers, adding to Office documents
- documents [Office development in Visual Studio], adding headers
- documents [Office development in Visual Studio], adding footers
- footers, adding to documents
ms.assetid: c7a5cc8a-d8c0-48e9-81d3-108aa6bfbb74
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b0f2651fc4bfedab3c7308c7fa7e8cef604666f0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-headers-and-footers-to-documents"></a>Postupy: Přidávání hlaviček a zápatí do dokumentů prostřednictvím kódu programu
  Můžete přidat text záhlaví a zápatí stránky v dokumentu s použitím <xref:Microsoft.Office.Interop.Word.Section.Headers%2A> vlastnost a <xref:Microsoft.Office.Interop.Word.Section.Footers%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Section>. Každá část dokument obsahuje tři záhlaví a zápatí stránky:  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterPrimary>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterEvenPages>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterFirstPage>  
  
 Postupy se liší pro přizpůsobení na úrovni dokumentu a doplňků VSTO.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customizations"></a>Přizpůsobení na úrovni dokumentu  
 Pokud chcete použít následující ukázky kódu, spusťte z `ThisDocument` třídy ve vašem projektu.  
  
#### <a name="to-add-text-to-footers-in-the-document"></a>Chcete-li přidat text do zápatí stránky do dokumentu  
  
1.  Následující příklad kódu nastaví písmo textu má být vložen do primární zápatí každé části dokumentu a poté vloží text do zápatí.  
  
     [!code-vb[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#114)]  
  
#### <a name="to-add-text-to-headers-in-the-document"></a>Chcete-li přidat text na záhlaví v dokumentu  
  
1.  Následující příklad kódu přidá pole, které chcete zobrazit číslo stránky v záhlaví v dokumentu a poté nastaví zarovnání odstavce tak, že text zarovnán napravo od záhlaví.  
  
     [!code-vb[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#116)]  
  
## <a name="vsto-add-ins"></a>Doplňků VSTO  
 Pokud chcete použít následující ukázky kódu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
#### <a name="to-add-text-to-footers-in-a-document"></a>Chcete-li přidat text do zápatí stránky v dokumentu  
  
1.  Následující příklad kódu nastaví písmo textu má být vložen do primární zápatí každé části dokumentu a poté vloží text do zápatí. Tento příklad kódu používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#114)]  
  
#### <a name="to-add-text-to-headers-in-the-document"></a>Chcete-li přidat text na záhlaví v dokumentu  
  
1.  Následující příklad kódu přidá pole, které chcete zobrazit číslo stránky v záhlaví v dokumentu a poté nastaví zarovnání odstavce tak, že text zarovnán napravo od záhlaví. Tento příklad kódu používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#116)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)  
   