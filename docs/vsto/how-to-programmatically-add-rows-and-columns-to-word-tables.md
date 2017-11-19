---
title: "Postupy: Programové přidávání řádků a sloupců do tabulek aplikace Word | Microsoft Docs"
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
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
ms.assetid: 01a9b6ca-1373-4a6e-b9e6-2225a1321daf
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bbe1ad8bea69f7d91b7796bae7cc03880fef7b04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>Postupy: Přidávání řádků a sloupců do tabulek aplikace Word prostřednictvím kódu programu
  V tabulce aplikace Microsoft Office Word buněk jsou uspořádány do řádků a sloupců. Můžete použít <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Rows> objekt, který chcete přidat řádků do tabulky a <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Columns> objekt, který chcete přidat sloupce.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customization-examples"></a>Příklady přizpůsobení na úrovni dokumentu  
 Následující příklady kódu lze použít v přizpůsobení na úrovni dokumentu. Pokud chcete použít tyto příklady, spusťte z `ThisDocument` třídy ve vašem projektu. Těchto příkladech se předpokládá, že je dokument spojené s vlastní již minimálně jedna tabulka.  
  
> [!IMPORTANT]  
>  Tento kód spustí jenom v projektech, které vytvoříte pomocí některé z následujících šablon projektu:  
>   
>  -   Dokument aplikace Word 2013  
> -   Šablona Wordu 2013  
> -   Dokument aplikace Word 2010  
> -   Šablona aplikace Word 2010  
>   
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení přidání řádků a sloupců do tabulky. Další informace najdete v tématu [postup: cíl aplikací prostřednictvím primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz sestavení aplikace Word 2010 primární zprostředkovatel komunikace s objekty](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
#### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda řádek přidáte do tabulky.  
  
     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupce do tabulky  
  
1.  Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak použít <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce šířku stejné.  
  
     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]  
  
## <a name="vsto-add-in-examples"></a>Příklady doplňku VSTO  
 Můžete použít následující příklady kódu v doplňku VSTO. Pokud chcete použít v příkladech, spusťte z `ThisAddIn` třídy ve vašem projektu. Těchto příkladech se předpokládá, že aktivní dokument už má alespoň jedna tabulka.  
  
> [!IMPORTANT]  
>  Tento kód spustí jenom v projektech, které vytvoříte pomocí šablony doplňku VSTO pro Word.  
>   
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení přidání řádků a sloupců do tabulky. Další informace najdete v tématu [postup: cíl aplikací prostřednictvím primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz sestavení aplikace Word 2010 primární zprostředkovatel komunikace s objekty](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
#### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda řádek přidáte do tabulky.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupce do tabulky  
  
1.  Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak použít <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce šířku stejné.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-create-word-tables.md)   
 [Postupy: přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Postupy: naplnění prostřednictvím kódu programu tabulek aplikace Word prostřednictvím vlastnosti dokumentu](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  