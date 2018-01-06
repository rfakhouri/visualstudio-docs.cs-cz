---
title: "Postupy: hledání prostřednictvím kódu programu a nahrazení textu v dokumentech | Microsoft Docs"
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
- documents [Office development in Visual Studio], searching
- text searches, replacing text
- text searches, documents
- text [Office development in Visual Studio], searching in documents
- text [Office development in Visual Studio], text searches
ms.assetid: a66962f5-eeb9-4dc6-a70f-9039ab437a63
caps.latest.revision: "51"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3ce2298ee213e310409dd904acb342e390cb1db2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-search-for-and-replace-text--in-documents"></a>Postupy: Hledání a nahrazování textu v dokumentech prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Word.Find> Objektu je členem obou <xref:Microsoft.Office.Interop.Word.Selection> a <xref:Microsoft.Office.Interop.Word.Range> objektů a vy můžete použít některý pro hledání textu v dokumentech aplikace Microsoft Office Word. Příkaz replace je rozšířením příkaz find.  
  
 Použít <xref:Microsoft.Office.Interop.Word.Find> objekt můžete procházet dokument aplikace Microsoft Office Word a vyhledat konkrétní text, formátování a stylu a použít <xref:Microsoft.Office.Interop.Word.Find.Replacement%2A> vlastnost, která má nahradit libovolný nalezených položek.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-a-selection-object"></a>Pomocí výběr objektu  
 Při použití <xref:Microsoft.Office.Interop.Word.Selection> objekt, který chcete najít text, všechny vyhledávací kritéria zadáte se uplatňuje se pouze na aktuálně vybraný text. Pokud <xref:Microsoft.Office.Interop.Word.Selection> je bod vložení, je prohledána dokumentu. Pokud byla položka nalezena odpovídající kritériím hledání, je automaticky vybrán.  
  
 Je důležité si uvědomit, že <xref:Microsoft.Office.Interop.Word.Find> kritéria jsou kumulativní, což znamená, že kritéria, jsou přidány do předchozí kritéria hledání. Vymazat formátování z předchozích hledání s použitím <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> metoda před hledání.  
  
#### <a name="to-find-text-using-a-selection-object"></a>Najít text s použitím výběr objektu  
  
1.  Proměnné přiřadíte hledaný řetězec.  
  
     [!code-vb[Trin_VstcoreWordAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#68)]
     [!code-csharp[Trin_VstcoreWordAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#68)]  
  
2.  Vymažte formátování z předchozích hledání.  
  
     [!code-vb[Trin_VstcoreWordAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#69)]
     [!code-csharp[Trin_VstcoreWordAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#69)]  
  
3.  Provést hledání a zobrazit okno se zprávou s výsledky.  
  
     [!code-vb[Trin_VstcoreWordAutomation#70](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#70)]
     [!code-csharp[Trin_VstcoreWordAutomation#70](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#70)]  
  
 Následující příklad ukazuje metodu dokončení.  
  
 [!code-vb[Trin_VstcoreWordAutomation#67](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#67)]
 [!code-csharp[Trin_VstcoreWordAutomation#67](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#67)]  
  
## <a name="using-a-range-object"></a>Pomocí objektu rozsahu  
 Použití <xref:Microsoft.Office.Interop.Word.Range> objektu umožňuje hledat text bez zobrazení nic v uživatelském rozhraní. <xref:Microsoft.Office.Interop.Word.Find> Objektu vrátí **True** Pokud je nalezen text, který odpovídá kritéria hledání a **False** Pokud neexistuje. Také přináší <xref:Microsoft.Office.Interop.Word.Range> objektu tak, aby odpovídaly kritériím hledání, pokud je nalezen text.  
  
#### <a name="to-find-text-using-a-range-object"></a>Najít text s použitím objektu rozsahu  
  
1.  Definování <xref:Microsoft.Office.Interop.Word.Range> objekt, který se skládá z druhé odstavce do dokumentu.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#72](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#72)]
     [!code-csharp[Trin_VstcoreWordAutomation#72](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#72)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento příklad používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#72](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#72)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#72](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#72)]  
  
2.  Pomocí <xref:Microsoft.Office.Interop.Word.Range.Find%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Range> objektu, nejprve zrušte všechny existující možnosti formátování a vyhledejte řetězec **mi najít**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#73](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#73)]
     [!code-csharp[Trin_VstcoreWordAutomation#73](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#73)]  
  
3.  Zobrazit výsledky hledání v okně se zprávou a vyberte <xref:Microsoft.Office.Interop.Word.Range> vytvořit viditelné.  
  
     [!code-vb[Trin_VstcoreWordAutomation#74](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#74)]
     [!code-csharp[Trin_VstcoreWordAutomation#74](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#74)]  
  
     Pokud se hledání nezdaří, je vybrána odstavec; Pokud se aktivace podaří, zobrazí se kritéria hledání.  
  
 Následující příklad ukazuje kód dokončení pro přizpůsobení na úrovni dokumentu. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#71](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#71)]
 [!code-csharp[Trin_VstcoreWordAutomation#71](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#71)]  
  
 Následující příklad ukazuje kód dokončení pro doplňku VSTO. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomationAddIn#71](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#71)]
 [!code-csharp[Trin_VstcoreWordAutomationAddIn#71](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#71)]  
  
## <a name="searching-for-and-replacing-text-in-documents"></a>Vyhledávání a nahrazování textu v dokumentech  
 Následující kód prohledá aktuální výběr a nahradí všechny výskyty řetězce **mi najít** řetězcem **nalezené**.  
  
#### <a name="to-search-for-and-replace-text-in-documents"></a>K vyhledání a nahrazení textu v dokumentech  
  
1.  Následující příklad kódu k přidání `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#75)]
     [!code-csharp[Trin_VstcoreWordAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#75)]  
  
     <xref:Microsoft.Office.Interop.Word.Find> Třída má <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> metody a <xref:Microsoft.Office.Interop.Word.Replacement> třída také obsahuje vlastní <xref:Microsoft.Office.Interop.Word.Replacement.ClearFormatting%2A> metoda. Při provádění operace hledání a nahrazování, musíte použít metodu ClearFormatting obou objektů. Pokud používáte pouze na <xref:Microsoft.Office.Interop.Word.Find> objekt, můžete získat neočekávané výsledky v Nahrazovací text.  
  
2.  Použití <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Find> objekt, který chcete nahradit každá položka nalezena. Chcete-li určit, které položky nahradit, použijte *nahradit* parametr. Tento parametr může být jeden z následujících <xref:Microsoft.Office.Interop.Word.WdReplace> hodnoty:  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceAll>nahradí všechny nalezené položky.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceNone>nahradí žádné nalezených položek.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceOne>nahradí první položka nalezena.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavování možností hledání v aplikaci Word](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Postupy: procházení nalezených položek v dokumentech prostřednictvím kódu programu cykly](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: programové obnovení výběru po hledání](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  