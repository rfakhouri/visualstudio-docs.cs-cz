---
title: 'Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu'
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
ms.openlocfilehash: 4caf48d0268e653b7ce6f7a5c8e7efb1e2ec39e6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257502"
---
# <a name="how-to-programmatically-print-visio-documents"></a>Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu
  Můžete vytisknout dokončení dokument aplikace Microsoft Office Visio nebo pouze konkrétní stránky.  
  
 Podrobnosti o tiskové metod najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff767996.aspx) metoda a [Microsoft.Office.Interop.Visio.Page.Print](https://msdn.microsoft.com/library/office/ff765064.aspx) – metoda .  
  
## <a name="print-a-visio-document"></a>Tisk dokumentů aplikace Visio  
  
### <a name="to-print-a-complete-document"></a>Tisk dokončení dokumentu  
  
-   Volání `Microsoft.Office.Interop.Visio.Document.Print` metodu `Microsoft.Office.Interop.Visio.Document` objekt, který chcete vytisknout.  
  
     Následující příklad kódu Vytiskne aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="print-a-page-of-a-visio-document"></a>Tisk – stránka dokumentů aplikace Visio  
  
### <a name="to-print-a-page-of-a-document"></a>K tisku stránky z dokumentu  
  
-   Volání `Microsoft.Office.Interop.Visio.Pages.Print` metodu `Microsoft.Office.Interop.Visio.Pages` objekt, který chcete vytisknout.  
  
     Následující příklad kódu se vytiskne na první stránku aktivní dokument. Pokud chcete použít v tomto příkladu, spustit kód `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  