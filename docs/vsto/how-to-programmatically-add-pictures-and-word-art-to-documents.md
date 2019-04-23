---
title: 'Postupy: Programové přidání obrázků a objektů WordArt do dokumentů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], adding pictures
- Word documents, adding pictures
- Word documents, adding Word Art
- graphics, adding to Word documents
- WordArt, adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f805153a35517c473e95beb871ae7d12a2776bd4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60043791"
---
# <a name="how-to-programmatically-add-pictures-and-word-art-to-documents"></a>Postupy: Programové přidání obrázků a objektů WordArt do dokumentů
  Obrázky a kresby můžete přidat do dokumentů v době návrhu nebo za běhu. WordArt umožňuje přidat dekorativní textu do dokumentů aplikace Microsoft Office Word. Tyto speciální textových efektů kreslení objekty, které můžete přizpůsobit a vložit do dokumentu.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="add-a-picture-at-design-time"></a>Přidat obrázek v době návrhu
 Pokud vyvíjíte přizpůsobení úrovni dokumentu, můžete přidat obrázek do dokumentu v době návrhu.

### <a name="to-add-a-picture-to-a-word-document-at-design-time"></a>Přidání obrázku do dokumentu aplikace Word v době návrhu

1. Umístěte ukazatel myši, kam chcete vložit obrázek v dokumentu.

2. Klikněte na tlačítko **vložit** kartu na pásu karet.

3. V **ilustrace** klikněte na možnost **obrázek**.

4. V **vložit obrázek** dialogové okno, přejděte na obrázek, který chcete vložit a klikněte na tlačítko **vložit**.

     Na obrázku se přidá do dokumentu na aktuální pozici kurzoru.

## <a name="add-a-picture-at-runtime"></a>Přidání obrázku za běhu
 Vložení obrázku do dokumentu na aktuální pozici kurzoru.

### <a name="to-add-a-picture-at-the-cursor-location"></a>Přidání obrázku v umístění kurzoru

1. Volání <xref:Microsoft.Office.Interop.Word.InlineShapes.AddPicture%2A> metodu <xref:Microsoft.Office.Interop.Word.InlineShapes> kolekce a předat mu název souboru.

     [!code-vb[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#108)]
     [!code-csharp[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#108)]

## <a name="add-wordart-at-design-time"></a>Přidat WordArt v době návrhu
 Pokud vyvíjíte přizpůsobení úrovni dokumentu, můžete přidat WordArt do dokumentů v době návrhu.

### <a name="to-add-wordart-to-a-word-document-at-design-time"></a>Chcete-li přidat WordArt do dokumentů aplikace Word v době návrhu

1. Umístěte ukazatel myši, kam chcete vložit WordArt do dokumentů.

2. Klikněte na tlačítko **vložit** kartu na pásu karet.

3. V **Text** klikněte na možnost **WordArt**a pak vyberte WordArt styl.

4. Text, který se má zobrazit v dokumentu, abychom **upravit WordArt Text** dialogové okno a klikněte na tlačítko **OK**.

     Text se přidá do dokumentu se vybrané WordArt stylem.

## <a name="add-wordart-at-runtime"></a>Přidat WordArt za běhu
 Vložte WordArt do dokumentů na aktuální pozici kurzoru. Postup se liší pro přizpůsobení na úrovni dokumentu a doplňky VSTO.

### <a name="to-add-wordart-at-the-cursor-location-in-a-document-level-customization"></a>Chcete-li přidat WordArt do umístění kurzoru v přizpůsobení na úrovni dokumentu

1. Získá pozici levém a horním aktuální umístění kurzoru.

     [!code-vb[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#109)]

2. Volání <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> metodu <xref:Microsoft.Office.Interop.Word.Shapes> objektu v dokumentu.

     [!code-vb[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#110)]

### <a name="to-add-wordart-at-the-cursor-location-in-a-vsto-add-in"></a>Chcete-li přidat WordArt na pozici kurzoru v doplňku VSTO

1. Získá pozici levém a horním aktuální umístění kurzoru.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#109)]

2. Volání <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> metodu <xref:Microsoft.Office.Interop.Word.Shapes> objektu aktivní dokument (nebo jiného dokumentu, který zadáte).

     [!code-vb[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#110)]

## <a name="compile-the-code"></a>Kompilace kódu

- Obrázek s názvem *SamplePicture.jpg* , musí existovat v jednotce C.

## <a name="see-also"></a>Viz také:
- [Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)
- [Postupy: Vkládání textu do dokumentů aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-insert-text-into-word-documents.md)
- [Postupy: Obnovení výběru po hledání prostřednictvím kódu programu](../vsto/how-to-programmatically-restore-selections-after-searches.md)
- [Postupy: Ukládání dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-documents.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
