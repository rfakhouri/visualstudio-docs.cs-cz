---
title: 'Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu smyčky'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 22f8035cc7c1b09e7fd54f3c10842237ee6273b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812407"
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu smyčky
  <xref:Microsoft.Office.Interop.Word.Find> Třída nemá <xref:Microsoft.Office.Interop.Word.Find.Found%2A> vlastnost, která vrací **true** vždy, když je položka hledané nalezena. Můžete projít všechny instance součástí <xref:Microsoft.Office.Interop.Word.Range> pomocí <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-loop-through-found-items"></a>K procházení nalezených položek

1. Deklarace <xref:Microsoft.Office.Interop.Word.Range> objektu.

    Následující příklad kódu je možné v přizpůsobení na úrovni dokumentu.

    [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
    [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]

    Následující příklad kódu je možné v doplňku VSTO. Tento příklad používá aktivní dokument.

    [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]

2. Použití <xref:Microsoft.Office.Interop.Word.Find.Found%2A> vlastnost ve smyčce a vyhledejte všechny výskyty řetězce v dokumentu a zvýšit proměnnou celého čísla 1 pokaždé, když je nalezen řetězec.

    [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
    [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]

3. Zobrazí počet pokusů, které řetězec se nenašel v okně se zprávou.

    [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
    [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]

   Následující příklady ukazují úplná metoda.

## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu

### <a name="to-loop-through-items-in-a-document-level-customization"></a>K vytvoření smyčky přes položky v přizpůsobení na úrovni dokumentu

1. Následující příklad ukazuje kompletní kód pro přizpůsobení na úrovni dokumentu. Chcete-li tento kód použít, spusťte z `ThisDocument` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="to-loop-through-items-in-a-vsto-add-in"></a>K vytvoření smyčky přes položky v doplňku VSTO

1. Následující příklad ukazuje kompletní kód doplňku VSTO. Chcete-li tento kód použít, spusťte z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově hledání a nahrazování rext v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Postupy: Nastavování možností hledání v aplikaci Word](../vsto/how-to-programmatically-set-search-options-in-word.md)
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Obnovení výběru po hledání prostřednictvím kódu programu](../vsto/how-to-programmatically-restore-selections-after-searches.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
