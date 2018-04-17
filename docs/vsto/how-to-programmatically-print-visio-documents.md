---
title: 'Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6efaffb9f8b3a9842528765d43f065acb314025f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-print-visio-documents"></a>Postupy: Tisk dokumentů aplikace Visio prostřednictvím kódu programu
  Můžete vytisknout dokončení dokument aplikace Microsoft Office Visio nebo pouze konkrétní stránky.  
  
 Podrobnosti o tiskové metod najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff767996.aspx) metoda a [Microsoft.Office.Interop.Visio.Page.Print](https://msdn.microsoft.com/library/office/ff765064.aspx) – metoda .  
  
## <a name="printing-a-visio-document"></a>Tisk dokumentů aplikace Visio  
  
#### <a name="to-print-a-complete-document"></a>Tisk dokončení dokumentu  
  
-   Volejte metodu Microsoft.Office.Interop.Visio.Document.Print Microsoft.Office.Interop.Visio.Document objektu, který chcete vytisknout.  
  
     Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="printing-a-page-of-a-visio-document"></a>Tisk na stránce dokumentů aplikace Visio  
  
#### <a name="to-print-a-page-of-a-document"></a>K tisku stránky z dokumentu  
  
-   Volejte metodu Microsoft.Office.Interop.Visio.Pages.Print Microsoft.Office.Interop.Visio.Pages objektu, který chcete vytisknout.  
  
     Následující příklad kódu se vytiskne na první stránku aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: Ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  