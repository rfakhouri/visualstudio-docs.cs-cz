---
title: "Postupy: přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu | Microsoft Docs"
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
- cells, adding text and formatting
- text [Office development in Visual Studio], adding to Word tables
- formatting [Office development in Visual Studio]
- tables [Office development in Visual Studio], adding text and formatting
ms.assetid: 3df6492a-dc9c-43ac-8fc3-0f944edd88b2
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ed593a9d03093fa092c97ce005ca190b5c433c8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables"></a>Postupy: Přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu
  Každá tabulka se skládá z kolekce buněk. Každé jednotlivé <xref:Microsoft.Office.Interop.Word.Cell> objekt představuje jednu buňku v tabulce. Odkazujete každá buňka její umístění v tabulce. Tento příklad se týká do buňky v prvním řádku a první sloupec tabulky; Přidá text do buňky; a použije formátování.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-add-text-and-formatting-to-cells"></a>K přidávání textu a formátování do buněk  
  
1.  Odkaz na buňku její umístění v tabulce, přidejte text do buňky a použít formátování.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#97)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument. Pokud chcete použít v příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#97)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-create-word-tables.md)   
 [Postupy: Programové přidávání řádků a sloupců do tabulek aplikace Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Postupy: Vkládání vlastností dokumentu do tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  