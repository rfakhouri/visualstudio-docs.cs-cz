---
title: "Postupy: ukládání dokumentů aplikace Visio prostřednictvím kódu programu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving Visio documents
- Visio [Office development in Visual Studio], saving Visio documents
ms.assetid: 1a29ac7e-1da4-4c7a-87a5-d3d16897fe7c
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a100a573f26a774c58083cb82b07c50792908f45
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-save-visio-documents"></a>Postupy: Ukládání dokumentů aplikace Visio prostřednictvím kódu programu
  Ukládání dokumentů aplikace Microsoft Office Visio několika způsoby:  
  
-   Uložení změn v stávající dokument.  
  
-   Uložit nový dokument nebo uložte dokument pod novým názvem.  
  
-   Uložte dokument se zadanými argumenty.  
  
 Další informace najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Document.Save](https://msdn.microsoft.com/library/office/ff766478.aspx) metody [Microsoft.Office.Interop.Visio.Document.SaveAs](https://msdn.microsoft.com/library/office/ff765824.aspx) metoda a [ Microsoft.Office.Interop.Visio.Document.SaveAsEx](https://msdn.microsoft.com/library/office/ff768149.aspx) metoda.  
  
## <a name="saving-an-existing-document"></a>Ukládání stávající dokument  
  
#### <a name="to-save-a-document"></a>Uložte dokument  
  
-   Volejte metodu Microsoft.Office.Interop.Visio.Document.Save třídy Microsoft.Office.Tools.Visio.Document dokumentu, který byl dříve uložili.  
  
     Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
    > [!NOTE]  
    >  Metoda Microsoft.Office.Interop.Visio.Document.Save vyvolá výjimku, pokud se nový dokument Visia dosud nebyl uložen.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#11)]  
  
## <a name="saving-a-document-with-a-new-name"></a>Ukládání dokument pod novým názvem.  
 Pomocí této metody Microsoft.Office.Interop.Visio.Document.SaveAs uložit nový dokument nebo dokument, který má nový název. Tato metoda je potřeba zadat nový název souboru.  
  
#### <a name="to-save-the-active-visio-document-with-a-new-name"></a>Uložte s novým názvem active dokumentů aplikace Visio  
  
-   Volání metody Microsoft.Office.Interop.Visio.Document.SaveAs Microsoft.Office.Tools.Visio.Document, který chcete uložit, a to pomocí plně kvalifikovanou cestu, včetně názvu souboru. Pokud soubor s tímto názvem již existuje v této složce, je bezobslužně přepsána.  
  
     Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#10)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#10)]  
  
## <a name="saving-a-document-with-a-new-name-and-specified-arguments"></a>Uložení dokumentu s novým názvem a zadané argumenty  
 Pomocí této metody Microsoft.Office.Interop.Visio.Document.SaveAsEx uložte dokument pod novým názvem a zadejte všechny příslušné argumenty použít k dokumentu.  
  
#### <a name="to-save-document-with-a-new-name-and-specified-arguments"></a>Uložte dokument s novým názvem a zadané argumenty  
  
-   Volání metody Microsoft.Office.Interop.Visio.Document.SaveAsEx Microsoft.Office.Tools.Visio.Document, který chcete uložit, a to pomocí plně kvalifikovanou cestu, včetně názvu souboru. Pokud soubor s tímto názvem již existuje v této složce, je vyvolána výjimka.  
  
     Následující příklad kódu uloží aktivní dokument pod novým názvem, označí dokumentu jako jen pro čtení a zobrazí dokument v seznamu naposledy použité dokumenty. Chcete-li použít tento příklad kódu, spusťte jej z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Uložte dokument, který má nový název, adresář s názvem `Test` musí být umístěný ve složce Dokumenty (pro Windows XP a starší) nebo ve složce Dokumenty (pro systém Windows Vista).  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  