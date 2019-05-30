---
title: Kopírování a vkládání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- shapes [Office development in Visual Studio], copying and pasting Visio shapes
- Visio [Office development in Visual Studio], copying and pasting Visio shapes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 074a276fe37ef713d38078f60c4bee95145c4d8b
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402226"
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>Postupy: Programově kopírování a vkládání obrazců do dokumentů aplikace Visio
  Programově můžete zkopírovat tvary na jedné stránce dokumentu a vložte je do novou stránku ve stejném dokumentu. Můžete vkládat do výchozího umístění (střední části okna aktivní) nebo do stejné souřadnice umístění měly na původní stránku.

## <a name="copy-and-paste-shapes"></a>Kopírování a vkládání obrazců
 Podrobnosti o objektovém modelu najdete v tématu referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](/office/vba/api/Visio.Shape.DrawRectangle), [Microsoft.Office.Interop.Visio.Shape.DrawOval](/office/vba/api/Visio.Shape.DrawOval), [ Microsoft.Office.Interop.Visio.Shape.Copy](/office/vba/api/Visio.Shape.Copy), a [Microsoft.Office.Interop.Visio.Shape.Paste](/office/vba/api/Visio.Shape.Paste) metody a [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](/office/vba/api/Visio.viscutcopypastecodes) příznak.

### <a name="to-copy-shapes-to-the-center-of-another-page"></a>Kopírování tvary do středu jinou stránku

- Následující příklad ukazuje, jak kopírovat tvary od první stránky a vkládat je do centra na druhé stránce.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]

## <a name="copy-and-paste-shapes-with-the-same-positions"></a>Kopírování a vkládání obrazců s na stejném místě
 Podrobnosti o objektovém modelu najdete v tématu referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](/office/vba/api/Visio.Shape.DrawRectangle), [Microsoft.Office.Interop.Visio.Shape.DrawOval](/office/vba/api/Visio.Shape.DrawOval), [ Microsoft.Office.Interop.Visio.Shape.Copy](/office/vba/api/Visio.Shape.Copy), a [Microsoft.Office.Interop.Visio.Shape.Paste](/office/vba/api/Visio.Shape.Paste) metody a [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](/office/vba/api/Visio.viscutcopypastecodes) příznak.

 Pokud je potřeba řídit formát vložených informací a (volitelně) vytvořit odkaz na zdrojový soubor (například dokument aplikace Microsoft Office Word), použijte metodu PasteSpecial.

### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>Zkopírujte tvary a umístění obrazce na jinou stránku

- Následující příklad ukazuje, jak zkopírovat tvary od první stránky a vložte je do druhé stránce s jejich původní souřadnici umístění.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]

## <a name="see-also"></a>Viz také:
- [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)
- [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)
- [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)
- [Postupy: Přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)
