---
title: 'Postupy: Vložení textu do dokumentů aplikace Word prostřednictvím kódu programu'
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, inserting text in documents
- text [Office development in Visual Studio], inserting in documents
- ranges, replacing text in documents
- documents [Office development in Visual Studio], inserting text
- text [Office development in Visual Studio], replacing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8ff5e0314e9834bd3d0f048bc82780d7e4af073d
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551813"
---
# <a name="how-to-programmatically-insert-text-into-word-documents"></a>Postupy: Vložení textu do dokumentů aplikace Word prostřednictvím kódu programu
  Existují tři základní způsoby, jak vložit text do systém Microsoft Office dokumentů aplikace Word:

- Vloží text do rozsahu.

- Nahradí text v rozsahu novým textem.

- <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> Použijte metodu <xref:Microsoft.Office.Interop.Word.Selection> objektu pro vložení textu na kurzor nebo výběr.

> [!NOTE]
> Můžete také vložit text do ovládacích prvků obsahu a záložek. Další informace naleznete v tématu [ovládací prvky obsahu](../vsto/content-controls.md) a [ovládací prvek záložek](../vsto/bookmark-control.md).

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="insert-text-in-a-range"></a>Vložení textu do rozsahu
 Pro vložení textu do dokumentu <xref:Microsoft.Office.Interop.Word.Range> použijte vlastnostobjektu.<xref:Microsoft.Office.Interop.Word.Range.Text%2A>

### <a name="to-insert-text-in-a-range"></a>Vložení textu do rozsahu

1. Zadejte rozsah na začátku dokumentu a vložte text **Nový**text.

     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.

     [!code-vb[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#51)]

     V doplňku VSTO se dá použít následující příklad kódu. Tento kód používá aktivní dokument.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#51)]

2. <xref:Microsoft.Office.Interop.Word.Range> Vyberte objekt, který se rozšíří z jednoho znaku na délku vloženého textu.

     [!code-vb[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#52)]
     [!code-csharp[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#52)]

## <a name="replace-text-in-a-range"></a>Nahrazení textu v rozsahu
 Pokud zadaný rozsah obsahuje text, bude veškerý text v rozsahu nahrazen vloženým textem.

### <a name="to-replace-text-in-a-range"></a>Nahrazení textu v rozsahu

1. <xref:Microsoft.Office.Interop.Word.Range> Vytvoří objekt, který se skládá z prvních 12 znaků v dokumentu.

     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.

     [!code-vb[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#53)]

     V doplňku VSTO se dá použít následující příklad kódu. Tento kód používá aktivní dokument.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#53)]

2. Nahraďte tyto znaky **novým textovým**řetězcem.

     [!code-vb[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#54)]
     [!code-csharp[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#54)]

3. Vyberte rozsah.

     [!code-vb[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#55)]
     [!code-csharp[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#55)]

## <a name="insert-text-using-typetext"></a>Vložení textu pomocí TypeText
 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> Metoda vloží text na výběr. <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>se chová odlišně v závislosti na možnostech nastavených v počítači uživatele. Kód v následujícím postupu deklaruje <xref:Microsoft.Office.Interop.Word.Selection> proměnnou objektu a vypne možnost přepisování, pokud je zapnutá. Pokud je aktivována možnost přepisování, je text vedle kurzoru přepsán.

### <a name="to-insert-text-using-the-typetext-method"></a>Vložení textu pomocí metody TypeText

1. Deklarujte <xref:Microsoft.Office.Interop.Word.Selection> proměnnou objektu.

    [!code-vb[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#57)]
    [!code-csharp[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#57)]

2. Vypněte možnost **přepisování** , pokud je zapnutá.

    [!code-vb[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#58)]
    [!code-csharp[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#58)]

3. Ověřte, zda je aktuální výběr místem vložení.

    Pokud je, kód vloží větu pomocí <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>a pak znak odstavce <xref:Microsoft.Office.Interop.Word.Selection.TypeParagraph%2A> pomocí metody.

    [!code-vb[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#59)]
    [!code-csharp[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#59)]

4. Kód v blocích Block Tests pro zjištění, zda je výběr normálního výběru. Pokud je, pak další testovací testy, abyste viděli, zda je zapnutá možnost **ReplaceSelection** . Pokud je, kód používá <xref:Microsoft.Office.Interop.Word.Selection.Collapse%2A> metodu výběru pro sbalení výběru na místo vložení na začátku vybraného bloku textu. Vložte text a značku odstavce.

    [!code-vb[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#60)]
    [!code-csharp[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#60)]

5. Pokud výběr není bod vložení nebo blok vybraného textu, pak kód v bloku **Else** neprovede žádnou akci.

    [!code-vb[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#61)]
    [!code-csharp[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#61)]

   Můžete také použít <xref:Microsoft.Office.Interop.Word.Selection.TypeBackspace%2A> metodu <xref:Microsoft.Office.Interop.Word.Selection> objektu, která napodobuje funkčnost klávesy **BACKSPACE** na klávesnici. Nicméně když přichází k vložení a manipulaci s textem, <xref:Microsoft.Office.Interop.Word.Range> objekt nabízí větší kontrolu.

   Následující příklad ukazuje úplný kód. Chcete-li použít tento příklad, spusťte kód z `ThisDocument` třídy `ThisAddIn` nebo v projektu.

   [!code-vb[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#56)]
   [!code-csharp[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#56)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programové formátování textu v dokumentech](../vsto/how-to-programmatically-format-text-in-documents.md)
- [Postupy: Programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Postupy: Programové rozšiřování oblastí v dokumentech](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
