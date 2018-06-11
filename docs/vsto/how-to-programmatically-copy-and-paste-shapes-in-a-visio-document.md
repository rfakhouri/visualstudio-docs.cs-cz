---
title: 'Postupy: programové kopírování a vkládání obrazců do dokumentů aplikace Visio'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- shapes [Office development in Visual Studio], copying and pasting Visio shapes
- Visio [Office development in Visual Studio], copying and pasting Visio shapes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 29dada62bb1e51c9cafb41d4eae08ce10e9a930c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257082"
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>Postupy: programové kopírování a vkládání obrazců do dokumentů aplikace Visio
  Můžete prostřednictvím kódu programu tvarů na jedné stránce dokumentu zkopírovat a vložit do jednoho dokumentu novou stránku. Můžete je vložit do výchozí umístění (center aktivní okno) nebo do stejné souřadnici umístění, jako měla na původní stránce.  
  
## <a name="copy-and-paste-shapes"></a>Kopírování a vkládání obrazců  
 Podrobnosti o objektu modelu najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), a [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) metody a [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](https://msdn.microsoft.com/library/office/ff765187.aspx) příznak.  
  
### <a name="to-copy-shapes-to-the-center-of-another-page"></a>Ke zkopírování obrazců do středu jinou stránku  
  
-   Následující příklad ukazuje, jak zkopírovat obrazce od první stránky a vložit do středu druhé stránce.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]  
  
## <a name="copy-and-paste-shapes-with-the-same-positions"></a>Kopírování a vkládání obrazců pomocí na stejném místě  
 Podrobnosti o objektu modelu najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx), [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx), [ Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx), a [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) metody a [ Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](https://msdn.microsoft.com/library/office/ff765187.aspx) příznak.  
  
 Pokud budete potřebovat kontrolu formátu vložených informací a (volitelně) vytvořit odkaz na zdrojový soubor (například dokument aplikace Microsoft Office Word), použijte metodu PasteSpecial.  
  
### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>Zkopírujte tvarů a tvar umístění na jinou stránku  
  
-   Následující příklad ukazuje, jak zkopírovat obrazce od první stránky a vložit je na druhé stránce s původních souřadnici umístění.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)   
 [Postupy: přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  