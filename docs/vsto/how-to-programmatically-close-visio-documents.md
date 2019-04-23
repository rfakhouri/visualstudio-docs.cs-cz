---
title: 'Postupy: Zavírání dokumentů aplikace Visio prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing Visio documents
- Visio [Office development in Visual Studio], closing Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 474efcb62cf7cadd9de82e41ff2ad36cebc046cb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60067652"
---
# <a name="how-to-programmatically-close-visio-documents"></a>Postupy: Zavírání dokumentů aplikace Visio prostřednictvím kódu programu
  Můžete zavřít aktivní dokument aplikace Microsoft Office Visio pomocí `Microsoft.Office.Interop.Visio.Document.Close` metody.

 Podrobnosti o této metodě naleznete v referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Document.Close](/office/vba/api/Visio.Document.Close) metody.

## <a name="close-the-active-document"></a>Zavřít aktivní dokument

### <a name="to-close-the-active-document"></a>Zavření aktivního dokumentu

- Volání `Microsoft.Office.Interop.Visio.Document.Close` metoda zavřít aktivní dokument.

     Chcete-li použít následující příklad kódu, spusťte `ThisAddIn` třídy v projektu doplňku VSTO pro Visio.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]

## <a name="see-also"></a>Viz také:
- [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)
- [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)
- [Postupy: Vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)
- [Postupy: Otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)
- [Postupy: Ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)
- [Postupy: Tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)
