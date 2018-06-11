---
title: 'Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing Visio documents
- Visio [Office development in Visual Studio], closing Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 153c9c3e32252f21dafd5b2d6bd6eb8ec1752161
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257862"
---
# <a name="how-to-programmatically-close-visio-documents"></a>Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu
  Aktivní dokument aplikace Microsoft Office Visio můžete zavřít pomocí `Microsoft.Office.Interop.Visio.Document.Close` metoda.  
  
 Podrobnosti o této metodě najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Document.Close](http://msdn.microsoft.com/library/office/ff767415.aspx) metoda.  
  
## <a name="close-the-active-document"></a>Zavře aktivní dokument.  
  
### <a name="to-close-the-active-document"></a>Zavření aktivního dokumentu  
  
-   Volání `Microsoft.Office.Interop.Visio.Document.Close` metodu zavře aktivní dokument.  
  
     Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro aplikaci Visio.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  