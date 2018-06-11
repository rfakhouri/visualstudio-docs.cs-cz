---
title: 'Postupy: programové vyloučení značek odstavů při vytváření oblastí'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], excluding paragraphs
- ranges, excluding paragraph marks in Word
- documents [Office development in Visual Studio], paragraph marks
- paragraphs, controlling structure
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6133249720711a057ed66516571563f8a5ee0db9
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256959"
---
# <a name="how-to-programmatically-exclude-paragraph-marks-when-creating-ranges"></a>Postupy: programové vyloučení značek odstavů při vytváření oblastí
  Vždy, když vytvoříte <xref:Microsoft.Office.Interop.Word.Range> objekt v závislosti na odstavce, všechny netisknutelné znaky, jako je například značky odstavce, jsou zahrnuty v rozsahu. Chcete vložit text ze zdroje odstavce do cílového odstavce. Pokud nechcete rozdělení cílového odstavce na samostatné odstavce, pak je nutné nejprve odstranit značku odstavce z odstavce zdroje. Navíc vzhledem k tomu, že informace o formátování odstavce je uložena v rámci značku odstavce, nemusí chcete být při vložení rozsahu do existujícího odstavce.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Následující ukázkový postup deklaruje dvě proměnné řetězec, načte obsah odstavců první a druhý v aktivním dokumentu a poté výměny jejich obsah. Příklad ukazuje pak odebrání značky odstavce z rozsahu pomocí <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metoda a vkládání textu uvnitř odstavce.  
  
## <a name="to-control-paragraph-structure-when-inserting-text"></a>K řízení odstavce struktura při vkládání textu  
  
1.  Vytvořte dvě proměnné rozsahu pro první a druhý odstavec a načíst jejich obsah, pomocí <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost.  
  
     Následující příklad kódu lze použít v přizpůsobení na úrovni dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#27)]
     [!code-csharp[Trin_VstcoreWordAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#27)]  
  
     Následující příklad kódu lze v doplňku VSTO úrovni aplikace. Tento kód používá aktivní dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#27)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#27](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#27)]  
  
2.  Přiřazení <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost, odkládací text mezi dva odstavce.  
  
     [!code-vb[Trin_VstcoreWordAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#28)]
     [!code-csharp[Trin_VstcoreWordAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#28)]  
  
3.  Pak vyberte všechny rozsahy a pozastavení zobrazíte výsledky v okně se zprávou.  
  
     [!code-vb[Trin_VstcoreWordAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#29)]
     [!code-csharp[Trin_VstcoreWordAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#29)]  
  
4.  Upravit `firstRange` pomocí <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metoda tak, aby značku odstavce již není součástí `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#30)]
     [!code-csharp[Trin_VstcoreWordAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#30)]  
  
5.  Nahradit zbývající část textu v prvním odstavci, přiřazení nové řetězec tak, aby <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#31)]
     [!code-csharp[Trin_VstcoreWordAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#31)]  
  
6.  Nahraďte text v `secondRange`, včetně značku odstavce.  
  
     [!code-vb[Trin_VstcoreWordAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#32)]
     [!code-csharp[Trin_VstcoreWordAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#32)]  
  
7.  Vyberte `firstRange` a pozastavení zobrazíte výsledky v okně se zprávou, a poté proveďte totožný s `secondRange`.  
  
     Vzhledem k tomu `firstRange` byl předefinovat vyloučit značku odstavce, se zachová původní formátování odstavce. Ale vložení věty přes značku odstavce v `secondRange`, odebrání samostatných odstavce.  
  
     [!code-vb[Trin_VstcoreWordAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#33)]
     [!code-csharp[Trin_VstcoreWordAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#33)]  
  
     Původní obsah obou rozsahy se uložily jako řetězce, aby bylo možné obnovit do původního stavu dokumentu.  
  
8.  Znovu nastavte `firstRange` zahrnout značku odstavce pomocí <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> metodu pro pozici o jeden znak.  
  
     [!code-vb[Trin_VstcoreWordAutomation#34](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#34)]
     [!code-csharp[Trin_VstcoreWordAutomation#34](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#34)]  
  
9. Odstraňte `secondRange`. Tím se obnoví odstavce tři na původní pozici.  
  
     [!code-vb[Trin_VstcoreWordAutomation#35](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#35)]
     [!code-csharp[Trin_VstcoreWordAutomation#35](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#35)]  
  
10. Obnovit původní text odstavce v `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#36](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#36)]
     [!code-csharp[Trin_VstcoreWordAutomation#36](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#36)]  
  
11. Použití <xref:Microsoft.Office.Interop.Word.Range.InsertAfter%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objekt, který chcete vložit původní obsah dva odstavce po `firstRange`a potom vyberte `firstRange`.  
  
     [!code-vb[Trin_VstcoreWordAutomation#37](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#37)]
     [!code-csharp[Trin_VstcoreWordAutomation#37](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#37)]  
  
## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="to-control-paragraph-structure-when-inserting-text-in-document-level-customizations"></a>K řízení odstavce struktura při vkládání textu v přizpůsobeních na úrovni dokumentu  
  
1.  Následující příklad ukazuje metodu dokončení pro přizpůsobení na úrovni dokumentu. Chcete-li použít tento kód, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#26)]
     [!code-csharp[Trin_VstcoreWordAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#26)]  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="to-control-paragraph-structure-when-inserting-text-in-an-vsto-add-in"></a>K řízení odstavce struktura při vkládání textu v doplňku VSTO  
  
1.  Následující příklad ukazuje metodu dokončení pro doplňku VSTO. Chcete-li použít tento kód, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#26)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#26](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#26)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: sbalení prostřednictvím kódu programu oblastí nebo výběrů v dokumentech](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Postupy: programové vkládání textu do dokumentů aplikace Word](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Postupy: programové resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  