---
title: 'Postupy: programové definování a výběr oblastí v dokumentech'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], selecting sentences
- documents [Office development in Visual Studio], ranges
- sentences, selecting in documents
- ranges, selecting in documents
- ranges, defining in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 947232d593543276de281d89e3d05d6648f29ec1
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257293"
---
# <a name="how-to-programmatically-define-and-select-ranges-in-documents"></a>Postupy: programové definování a výběr oblastí v dokumentech
  Můžete definovat rozsah v dokumentu aplikace Microsoft Office Word pomocí <xref:Microsoft.Office.Interop.Word.Range> objektu. Můžete vybere celý dokument v mnoha způsoby, například pomocí <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objektu, nebo pomocí vlastnost obsahu <xref:Microsoft.Office.Tools.Word.Document> – třída (v přizpůsobení na úrovni dokumentu) nebo <xref:Microsoft.Office.Interop.Word.Document> – třída (v Doplňku VSTO).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="define-a-range"></a>Definujte rozsah  
 Následující příklad ukazuje, jak vytvořit nový <xref:Microsoft.Office.Interop.Word.Range> objekt, který obsahuje první sedm znaků v aktivním dokumentu, včetně netisknutelné znaky. Vybere text v rozsahu.  
  
### <a name="to-define-a-range-in-a-document-level-customization"></a>Chcete-li definovat rozsah v přizpůsobení na úrovni dokumentu  
  
1.  Přidat rozsah do dokumentu pomocí předání počáteční a koncové znak pro <xref:Microsoft.Office.Tools.Word.Document.Range%2A> metodu <xref:Microsoft.Office.Tools.Word.Document> třídy. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#18)]  
  
### <a name="to-define-a-range-by-using-a-vsto-add-in"></a>Chcete-li definovat rozsah pomocí doplňku VSTO  
  
1.  Přidat rozsah do dokumentu pomocí předání počáteční a koncové znak pro <xref:Microsoft.Office.Interop.Word._Document.Range%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> třídy. Následující příklad kódu přidá rozsah pro aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#18)]  
  
## <a name="select-a-range-in-a-document-level-customization"></a>Vybrat rozsah, v přizpůsobení na úrovni dokumentu  
 Následující příklady ukazují, jak pomocí vybere celý dokument <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objektu, nebo pomocí <xref:Microsoft.Office.Tools.Word.Document.Content%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Document> – třída.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Vyberte celý dokument jako rozsah pomocí metody Select  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> obsahující celý dokument. Chcete-li použít následující příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Celý dokument vybrat jako rozsah pomocí vlastnosti obsahu  
  
1.  Použití <xref:Microsoft.Office.Tools.Word.Document.Content%2A> vlastnost definovat rozsah, který zahrnuje celý dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#20)]
     [!code-csharp[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#20)]  
  
 Pro určení rozsahu můžete také použít metody a vlastnosti jiné objekty.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Chcete-li vybrat věty v aktivním dokumentu.  
  
1.  Nastavit rozsah pomocí <xref:Microsoft.Office.Interop.Word.Sentences> kolekce. Použijte index věty, které chcete vybrat.  
  
     [!code-vb[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#21)]
     [!code-csharp[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#21)]  
  
 Jiný způsob, jak vybrat větu je ručně nastavit počáteční a koncové hodnoty pro rozsah.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Chcete-li vybrat věty ručně nastavte počáteční a koncové hodnoty  
  
1.  Vytvořte proměnnou rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#23)]  
  
2.  Zkontrolujte, zda existují alespoň dvě věty v dokumentu, nastavte *spustit* a *End* argumenty rozsahu, a potom vyberte rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#24)]  
  
## <a name="select-a-range-by-using-a-vsto-add-in"></a>Výběr rozsahu pomocí doplňku VSTO  
 Následující příklady ukazují, jak pomocí vybere celý dokument <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> objektu, nebo pomocí <xref:Microsoft.Office.Interop.Word._Document.Content%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Document> – třída.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Vyberte celý dokument jako rozsah pomocí metody Select  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Range.Select%2A> metodu <xref:Microsoft.Office.Interop.Word.Range> obsahující celý dokument. Následující příklad kódu vybere obsah aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>Celý dokument vybrat jako rozsah pomocí vlastnosti obsahu  
  
1.  Použití <xref:Microsoft.Office.Interop.Word._Document.Content%2A> vlastnost definovat rozsah, který zahrnuje celý dokument.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#20)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#20)]  
  
 Pro určení rozsahu můžete také použít metody a vlastnosti jiné objekty.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Chcete-li vybrat věty v aktivním dokumentu.  
  
1.  Nastavit rozsah pomocí <xref:Microsoft.Office.Interop.Word.Sentences> kolekce. Použijte index věty, které chcete vybrat.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#21)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#21)]  
  
 Jiný způsob, jak vybrat větu je ručně nastavit počáteční a koncové hodnoty pro rozsah.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Chcete-li vybrat věty ručně nastavte počáteční a koncové hodnoty  
  
1.  Vytvořte proměnnou rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#23)]  
  
2.  Zkontrolujte, zda existují alespoň dvě věty v dokumentu, nastavte *spustit* a *End* argumenty rozsahu, a potom vyberte rozsahu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#24)]  
  
## <a name="see-also"></a>Viz také:  
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: načítání počátečních a koncových znaků v oblastech prostřednictvím kódu programu](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Postupy: rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Postupy: programové resetování oblastí v dokumentech aplikace Word](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Postupy: sbalení prostřednictvím kódu programu oblastí nebo výběrů v dokumentech](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Postupy: programové vyloučení značek odstavů při vytváření oblastí](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  