---
title: 'Postupy: Vytváření nových dokumentů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 882183d1e23168e1a3a833cd7cc723f28ce1a139
ms.sourcegitcommit: 73861cd0ea92e50a3be1ad2a0ff0a7b07b057a1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2019
ms.locfileid: "54154119"
---
# <a name="how-to-programmatically-create-new-documents"></a>Postupy: Vytváření nových dokumentů prostřednictvím kódu programu
  Při vytváření dokumentů prostřednictvím kódu programu, nový dokument je nativní <xref:Microsoft.Office.Interop.Word.Document> objektu. Tento objekt nemá žádné další události a možnosti vázání dat z <xref:Microsoft.Office.Tools.Word.Document> hostitelský objekt. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Když vyvíjíte projekt úrovni dokumentu, nelze programově přidat <xref:Microsoft.Office.Tools.Word.Document> hostovat položky do projektu. V projektu doplňku VSTO, můžete převést všechny <xref:Microsoft.Office.Interop.Word.Document> do objektu <xref:Microsoft.Office.Tools.Word.Document> hostitelské položky v době běhu. Další informace najdete v tématu [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="to-create-a-new-document-based-on-the-normal-template"></a>Chcete-li vytvořit nový dokument založený na šabloně Normální  
  
-   Použití <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Documents> kolekce vytvoříte nový textový dokument založený na šabloně Normální. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]  
  
## <a name="use-custom-templates"></a>Používat vlastní šablony  
 <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> Metoda má volitelnou *šablony* argument vytvoříte nový textový dokument založený na šabloně než normální šablony. Musíte zadat název souboru a plně kvalifikovanou cestu šablony.  
  
### <a name="to-create-a-new-document-based-on-a-custom-template"></a>Chcete-li vytvořit nový dokument založený na vlastní šabloně  
  
-   Volání <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Documents> kolekce a zadejte cestu k šabloně. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídu ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
