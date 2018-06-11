---
title: 'Postupy: programové vkládání textu do dokumentů aplikace Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 331fa8a91bb4fff51cb59b7a9f3cce23a38b3d2e
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257209"
---
# <a name="how-to-programmatically-insert-text-into-word-documents"></a>Postupy: programové vkládání textu do dokumentů aplikace Word
  Vkládání textu do dokumentů aplikace Microsoft Office Word tři primární způsoby:  
  
-   Vložte text v rozsahu.  
  
-   Nahraďte text v rozsahu nového textu.  
  
-   Použití <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> metodu <xref:Microsoft.Office.Interop.Word.Selection> objekt, který chcete vložit text v kurzoru nebo výběru.  
  
> [!NOTE]  
>  Můžete také vložit text do ovládacích prvků obsahu a záložky. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md) a [Bookmark – ovládací prvek](../vsto/bookmark-control.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="insert-text-in-a-range"></a>Zadejte text v rozsahu  
 Použití <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Range> objekt, který chcete vložit text v dokumentu.  
  
### <a name="to-insert-text-in-a-range"></a>Chcete-li vložit text v rozsahu  
  
1.  Zadejte rozsah na začátku dokumentu a vložit text **nového textu**.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#51)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento kód používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#51)]  
  
2.  Vyberte <xref:Microsoft.Office.Interop.Word.Range> objekt, který má na délku vložený text rozšířena z jeden znak.  
  
     [!code-vb[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#52)]
     [!code-csharp[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#52)]  
  
## <a name="replace-text-in-a-range"></a>Nahradí text v rozsahu  
 Pokud zadaný rozsah obsahuje text, veškerého textu v rozsahu se nahradí vložený text.  
  
### <a name="to-replace-text-in-a-range"></a>Chcete-li nahradit text v rozsahu  
  
1.  Vytvoření <xref:Microsoft.Office.Interop.Word.Range> objekt, který se skládá z prvních 12 znaků v dokumentu.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#53)]  
  
     Následující příklad kódu lze v doplňku VSTO. Tento kód používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#53)]  
  
2.  Nahraďte řetězec tyto znaky **nového textu**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#54)]
     [!code-csharp[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#54)]  
  
3.  Vyberte rozsah.  
  
     [!code-vb[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#55)]
     [!code-csharp[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#55)]  
  
## <a name="insert-text-using-typetext"></a>Vložit text s použitím TypeText  
 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> Metoda vloží text ve výběru. <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> pracuje odlišně v závislosti na možnostech nastavit v počítači uživatele. Kód v následujícím postupu deklaruje <xref:Microsoft.Office.Interop.Word.Selection> objektová proměnná a vypne zobrazování **přepisování** možnost, pokud je zapnutá. Pokud **přepisování** je aktivovaná možnost a potom se přepíše jakýkoli text vedle kurzor.  
  
### <a name="to-insert-text-using-the-typetext-method"></a>Chcete-li vložit text pomocí metody TypeText  
  
1.  Deklarace <xref:Microsoft.Office.Interop.Word.Selection> proměnné objektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#57)]
     [!code-csharp[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#57)]  
  
2.  Vypnout **přepisování** možnost, pokud je zapnutá.  
  
     [!code-vb[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#58)]
     [!code-csharp[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#58)]  
  
3.  Zkontrolujte, zda aktuální výběr je bod vložení.  
  
     Pokud se jedná, vloží kód větu pomocí <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>a potom odstavce označit použitím <xref:Microsoft.Office.Interop.Word.Selection.TypeParagraph%2A> metoda.  
  
     [!code-vb[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#59)]
     [!code-csharp[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#59)]  
  
4.  Kód **ElseIf –** blokovat otestuje, zda jedná o normální výběr. Pokud je, pak další **Pokud** blokovat otestuje, zda **ReplaceSelection** je zapnutá možnost. Pokud se jedná, kód používá <xref:Microsoft.Office.Interop.Word.Selection.Collapse%2A> metoda výběru na Sbalit výběr na bod vložení na začátku vybraného bloku textu. Vložte text a značku odstavce.  
  
     [!code-vb[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#60)]
     [!code-csharp[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#60)]  
  
5.  Pokud výběr není bod vložení nebo bloku vybraný text, pak se kód **Else** bloku se nic nestane.  
  
     [!code-vb[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#61)]
     [!code-csharp[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#61)]  
  
 Můžete také <xref:Microsoft.Office.Interop.Word.Selection.TypeBackspace%2A> metodu <xref:Microsoft.Office.Interop.Word.Selection> objektu, která napodobuje funkce **Backspace** klíče na klávesnici. Ale při rozhodování o vložení a manipulace s nimi text, <xref:Microsoft.Office.Interop.Word.Range> objekt nabízí větší kontrolu.  
  
 Následující příklad ukazuje kód dokončení. Pokud chcete použít v tomto příkladu, spustit kód `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#56)]
 [!code-csharp[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#56)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: formátování textu v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-format-text-in-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)  
  
  