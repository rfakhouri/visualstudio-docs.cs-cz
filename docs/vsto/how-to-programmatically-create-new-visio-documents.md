---
title: 'Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], creating Visio documents
- documents [Office development in Visual Studio], creating Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b5b66690d3856a2bf1fc6df417b60ab5e293127
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256741"
---
# <a name="how-to-programmatically-create-new-visio-documents"></a>Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu
  Když vytváříte vykreslení dokumentu nové aplikace Microsoft Office Visio, můžete ho přidat do `Microsoft.Office.Interop.Visio.Documents` kolekce otevřené dokumenty Visio. V důsledku toho `Microsoft.Office.Interop.Visio.Documents.Add` metoda vytvoří novou vykreslování dokumentů aplikace Visio. Další informace najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) metoda.  
  
## <a name="create-new-blank-documents"></a>Vytvoření nové prázdné dokumenty  
  
### <a name="to-create-a-new-document"></a>Chcete-li vytvořit nový dokument  
  
-   Použití `Microsoft.Office.Interop.Visio.Documents.Add` metodu pro vytvoření nového prázdného dokumentu, který není na základě šablony.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="create-documents-copied-from-existing-documents"></a>Vytváření dokumentů zkopírovány z existující dokumentů  
 `Microsoft.Office.Interop.Visio.Documents.Add` Metoda můžete vytvořit nový dokument, který je kopií existujícího dokumentu aplikace Visio. Je třeba zadat název souboru a plně kvalifikovanou cestu diagramu.  
  
### <a name="to-create-a-new-document-that-is-copied-from-an-existing-document"></a>Vytvořit nový dokument, který se zkopíruje z existujícího dokumentu  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metoda a zadejte cestu diagram aplikace Visio.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="create-stencils-copied-from-existing-stencils"></a>Vytvořit vzorníky zkopírovány z existující vzorníky  
 [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) metoda můžete vytvořit nový vzorník, který je kopií existujícího vzorníku aplikace Visio. Je třeba zadat název souboru a plně kvalifikovanou cestu vzorníku.  
  
### <a name="to-create-a-new-stencil-that-is-copied-from-an-existing-stencil"></a>Chcete-li vytvořit nový vzorník, která se zkopírují z existujícího vzorníku  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metoda a zadejte cestu vzorníku.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="create-documents-based-on-existing-templates"></a>Vytváření dokumentů na základě existujících šablon  
 `Microsoft.Office.Interop.Visio.Documents.Add` Metoda můžete vytvořit nový dokument ( *.vsd* souboru) založený na existující šablony aplikace Visio ( *vst* souboru). Tato metoda zkopíruje vzorníky, styly a nastavení, které jsou součástí šablony pracovního prostoru. Je třeba zadat název souboru a plně kvalifikovanou cestu šablony.  
  
### <a name="to-create-a-new-document-that-is-based-on-an-existing-template"></a>Vytvořit nový dokument, který je založen na existující šablony  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metoda a zadat cestu k šabloně.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Dokumentů aplikace Visio s názvem `myDrawing.vsd` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složky (pro systém Windows Vista).  
  
-   Dokumentů aplikace Visio s názvem `myStencil.vss` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složky (pro systém Windows Vista).  
  
-   Dokumentů aplikace Visio s názvem `myTemplate.vst` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složky (pro systém Windows Vista).  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  