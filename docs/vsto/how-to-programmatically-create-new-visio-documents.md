---
title: 'Postupy: Vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], creating Visio documents
- documents [Office development in Visual Studio], creating Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 00f4c531b63ff9f07d08bde2f81dc083986252fe
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868600"
---
# <a name="how-to-programmatically-create-new-visio-documents"></a>Postupy: Vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu
  Když vytváříte vykreslení dokumentu nové aplikace Microsoft Office Visio, přidejte ji tak `Microsoft.Office.Interop.Visio.Documents` kolekce otevřených dokumentů aplikace Visio. V důsledku toho `Microsoft.Office.Interop.Visio.Documents.Add` metoda vytvoří nový dokument výkresu Visia. Další informace najdete v tématu referenční dokumentaci jazyka VBA pro [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) metody.  
  
## <a name="create-new-blank-documents"></a>Vytvoření nové prázdné dokumenty  
  
### <a name="to-create-a-new-document"></a>Chcete-li vytvořit nový dokument  
  
-   Použití `Microsoft.Office.Interop.Visio.Documents.Add` metodu pro vytvoření nového prázdného dokumentu, který není založen na šabloně.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="create-documents-copied-from-existing-documents"></a>Vytváření dokumentů, které jsou zkopírovány z existující dokumenty  
 `Microsoft.Office.Interop.Visio.Documents.Add` Metody můžete vytvořit nový dokument, který je kopii existující dokument Visia. Musíte zadat název souboru a diagram plně kvalifikovanou cestu.  
  
### <a name="to-create-a-new-document-that-is-copied-from-an-existing-document"></a>Chcete-li vytvořit nový dokument, který je zkopírován z existujícího dokumentu  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metodu a zadejte cestu k diagram Visia.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="create-stencils-copied-from-existing-stencils"></a>Vytvořit vzorníky zkopírovány z existující vzorníky  
 [Microsoft.Office.Interop.Visio.Documents.Add](/office/vba/api/Visio.Documents.Add) metody můžete vytvořit nové šablony hloubky, který je kopií existujícího vzorníku Visia. Musíte zadat název souboru a plně kvalifikovanou cestu vzorníku.  
  
### <a name="to-create-a-new-stencil-that-is-copied-from-an-existing-stencil"></a>Chcete-li vytvořit nový, který se zkopíruje z existující šablony hloubky vzorníku  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metodu a zadejte cestu k vzorníku.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="create-documents-based-on-existing-templates"></a>Vytváření dokumentů na základě existujících šablon  
 `Microsoft.Office.Interop.Visio.Documents.Add` Metody můžete vytvořit nový dokument ( *.vsd* souboru), který je založen na základě existující šablony Visio ( *vst* souboru). Tato metoda zkopíruje vzorníků, styly a nastavení, které jsou součástí šablony pracovního prostoru. Musíte zadat název souboru a plně kvalifikovanou cestu šablony.  
  
### <a name="to-create-a-new-document-that-is-based-on-an-existing-template"></a>Chcete-li vytvořit nový dokument, který je založen na základě existující šablony  
  
-   Volání `Microsoft.Office.Interop.Visio.Documents.Add` metodu a zadejte cestu k šabloně.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Dokument Visia s názvem `myDrawing.vsd` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složku (pro Windows Vista).  
  
-   Dokument Visia s názvem `myStencil.vss` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složku (pro Windows Vista).  
  
-   Dokument Visia s názvem `myTemplate.vst` musí být umístěn v adresáři s názvem `Test` v *dokumenty* složky (pro Windows XP a starší) nebo *dokumenty* složku (pro Windows Vista).  
  
## <a name="see-also"></a>Viz také:  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: Otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: Zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: Ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Postupy: Tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)  
