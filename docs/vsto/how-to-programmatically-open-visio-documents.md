---
title: 'Postupy: Otevírání dokumentů aplikace Visio prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b87d3b1659d46a69e5a2e950997d3c0474e84d11
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598385"
---
# <a name="how-to-programmatically-open-visio-documents"></a>Postupy: Otevírání dokumentů aplikace Visio prostřednictvím kódu programu
  Existují dvě metody pro otevírání stávajících dokumentů Microsoft Office Visio: Otevřít a OpenEx. Metoda OpenEx se shoduje s metodu Open s tím rozdílem, že obsahuje argumenty, ve kterých můžete určit volající, jak se dokument otevře.

 Podrobnosti o objektovém modelu najdete v tématu referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Documents.Open](/office/vba/api/Visio.Documents.Open) metoda a [Microsoft.Office.Interop.Visio.Documents.OpenEx](/office/vba/api/Visio.Documents.OpenEx) Metoda.

## <a name="open-a-visio-document"></a>Otevřete dokument Visia

### <a name="to-open-a-visio-document"></a>Otevřete dokument Visia

-   Volání `Microsoft.Office.Interop.Visio.Documents.Open` metodu a zadejte plně kvalifikovanou cestu dokument Visia.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]

## <a name="open-a-visio-document-with-specified-arguments"></a>Otevřete dokument Visia se zadanými argumenty

### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Otevřete dokument Visia jako jen pro čtení a ukotvených

-   Volání `Microsoft.Office.Interop.Visio.Documents.OpenEx` metoda, zadejte plně kvalifikovanou cestu dokumentů aplikace Visio a zahrnout argumenty, které chcete použít – v tomto případu, ukotvených a jen pro čtení.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad kódu vyžaduje následující:

-   Dokument Visia s názvem `myDrawing.vsd` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složku (pro Windows Vista).

## <a name="see-also"></a>Viz také:
- [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)
- [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)
- [Postupy: Vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)
- [Postupy: Zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)
- [Postupy: Ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)
- [Postupy: Tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)
