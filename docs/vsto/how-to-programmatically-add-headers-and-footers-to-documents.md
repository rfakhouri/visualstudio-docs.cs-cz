---
title: 'Postupy: Programové přidání záhlaví a zápatí do dokumentů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- headers, adding to Office documents
- documents [Office development in Visual Studio], adding headers
- documents [Office development in Visual Studio], adding footers
- footers, adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7859657b52e5d96280646387f70686d2804e6fe7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967618"
---
# <a name="how-to-programmatically-add-headers-and-footers-to-documents"></a>Postupy: Programové přidání záhlaví a zápatí do dokumentů
  Můžete přidat text záhlaví a zápatí v dokumentu s použitím <xref:Microsoft.Office.Interop.Word.Section.Headers%2A> vlastnost a <xref:Microsoft.Office.Interop.Word.Section.Footers%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Section>. Každá část dokumentu obsahuje tři záhlaví a zápatí:

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterPrimary>

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterEvenPages>

- <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterFirstPage>

  Postupy se liší pro přizpůsobení na úrovni dokumentu a doplňky VSTO.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="document-level-customizations"></a>Přizpůsobení na úrovni dokumentu
 Pokud chcete použít následující příklady kódu, spustit je z `ThisDocument` třídu ve vašem projektu.

### <a name="to-add-text-to-footers-in-the-document"></a>Chcete-li přidat text zápatí v dokumentu

1. Následující příklad kódu nastaví písmo textu má být vložen do primární zápatí každá část dokumentu a pak vloží text do zápatí.

     [!code-vb[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#114)]

### <a name="to-add-text-to-headers-in-the-document"></a>Chcete-li přidat text do hlavičky v dokumentu

1. Následující příklad kódu přidá pole číslo stránky v záhlaví v dokumentu a pak nastaví zarovnání odstavce tak, že text zarovnán napravo od záhlaví.

     [!code-vb[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#116)]

## <a name="vsto-add-ins"></a>Doplňky VSTO
 Pokud chcete použít následující příklady kódu, spustit je z `ThisAddIn` třídu ve vašem projektu.

### <a name="to-add-text-to-footers-in-a-document"></a>Chcete-li přidat text zápatí v dokumentu

1. Následující příklad kódu nastaví písmo textu má být vložen do primární zápatí každá část dokumentu a pak vloží text do zápatí. Tento příklad kódu používá aktivního dokumentu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#114)]

### <a name="to-add-text-to-headers-in-the-document"></a>Chcete-li přidat text do hlavičky v dokumentu

1. Následující příklad kódu přidá pole číslo stránky v záhlaví v dokumentu a pak nastaví zarovnání odstavce tak, že text zarovnán napravo od záhlaví. Tento příklad kódu používá aktivního dokumentu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#116)]

## <a name="see-also"></a>Viz také:
- [Postupy: Vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)
- [Postupy: Rozšiřování oblastí v dokumentech prostřednictvím kódu programu](../vsto/how-to-programmatically-extend-ranges-in-documents.md)
- [Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu smyčky](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
