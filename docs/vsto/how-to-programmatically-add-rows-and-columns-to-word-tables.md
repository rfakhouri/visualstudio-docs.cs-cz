---
title: 'Postupy: Programové přidávání řádků a sloupců do tabulek aplikace Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 865a33e181d761665dbe2e44976f171a2b60d433
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255886"
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>Postupy: Programové přidávání řádků a sloupců do tabulek aplikace Word
  V tabulce aplikace Microsoft Office Word buněk jsou uspořádány do řádků a sloupců. Můžete použít <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Rows> objekt, který chcete přidat řádků do tabulky a <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Columns> objekt, který chcete přidat sloupce.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customization-examples"></a>Příklady přizpůsobení na úrovni dokumentu  
 Následující příklady kódu lze použít v přizpůsobení na úrovni dokumentu. Pokud chcete použít tyto příklady, spusťte z `ThisDocument` třídy ve vašem projektu. Těchto příkladech se předpokládá, že je dokument spojené s vlastní již minimálně jedna tabulka.  
  
> [!IMPORTANT]  
>  Tento kód spustí jenom v projektech, které vytvoříte pomocí některé z následujících šablon projektu:  
>   
> -   Dokument aplikace Word 2013  
> -   Šablona Wordu 2013  
> -   Dokument aplikace Word 2010  
> -   Šablona aplikace Word 2010  
>   
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení přidání řádků a sloupců do tabulky. Další informace najdete v tématu [postup: Office cíl aplikací prostřednictvím primárních sestavení vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [referenční primární spolupracující sestavení Wordu 2010](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda řádek přidáte do tabulky.  
  
     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]  
  
### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupce do tabulky  
  
1.  Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak použít <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce šířku stejné.  
  
     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]  
  
## <a name="vsto-add-in-examples"></a>Příklady doplňku VSTO  
 Můžete použít následující příklady kódu v doplňku VSTO. Pokud chcete použít v příkladech, spusťte z `ThisAddIn` třídy ve vašem projektu. Těchto příkladech se předpokládá, že aktivní dokument už má alespoň jedna tabulka.  
  
> [!IMPORTANT]  
>  Tento kód spustí jenom v projektech, které vytvoříte pomocí šablony doplňku VSTO pro Word.  
>   
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Word** sestavení a pak pomocí třídy z tohoto sestavení přidání řádků a sloupců do tabulky. Další informace najdete v tématu [postup: Office cíl aplikací prostřednictvím primárních sestavení vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [referenční primární spolupracující sestavení Wordu 2010](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
### <a name="to-add-a-row-to-a-table"></a>Chcete-li přidat řádek do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> metoda řádek přidáte do tabulky.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]  
  
### <a name="to-add-a-column-to-a-table"></a>Chcete-li přidat sloupce do tabulky  
  
1.  Použít <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> metoda a pak použít <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> metoda chcete, aby všechny sloupce šířku stejné.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: vytváření tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-create-word-tables.md)   
 [Postupy: přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Postupy: naplnění prostřednictvím kódu programu tabulek aplikace Word prostřednictvím vlastnosti dokumentu](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  