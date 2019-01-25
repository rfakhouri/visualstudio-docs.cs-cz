---
title: 'Postupy: Přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- cells, adding text and formatting
- text [Office development in Visual Studio], adding to Word tables
- formatting [Office development in Visual Studio]
- tables [Office development in Visual Studio], adding text and formatting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1bbebc1dd1173250ef6c4328916e1cee66b371c4
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54867231"
---
# <a name="how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables"></a>Postupy: Přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu
  Každá tabulka se skládá z kolekce buněk. Jednotlivých <xref:Microsoft.Office.Interop.Word.Cell> objekt představuje jednu buňku v tabulce. Na každé buňce její umístění v tabulce můžete odkazovat. V tomto příkladu odkazuje na buňku v prvním řádku a první sloupec tabulce. Přidá text do buňky; a použije formátování.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-add-text-and-formatting-to-cells"></a>Přidání textu a formátování do buněk  
  
1.  Odkaz na buňku její umístění v tabulce, přidejte text do buňky a použít formátování.  
  
     Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu. Pokud chcete použít tento příklad, spusťte jej z `ThisDocument` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#97)]  
  
     Následující příklad kódu je možné v doplňku VSTO. Tento příklad používá aktivní dokument. Pokud chcete použít v příkladu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#97)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Vytváření tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-create-word-tables.md)   
 [Postupy: Programové přidání řádků a sloupců do tabulek aplikace Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Postupy: Vkládání kódu programu s vlastností dokumentu do tabulek aplikace Word](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
