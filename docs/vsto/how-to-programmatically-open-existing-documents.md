---
title: 'Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 670c4855806dcc5d781da8479963f6705ba99fd3
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54869145"
---
# <a name="how-to-programmatically-open-existing-documents"></a>Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> Metoda otevře existující dokument aplikace Microsoft Office Word určené plně kvalifikovaný název a cesta k souboru. Tato metoda vrátí hodnotu <xref:Microsoft.Office.Interop.Word.Document> , která představuje otevřený dokument.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-open-a-document"></a>Chcete-li otevřít dokument  
  
-   Volání <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> metodu <xref:Microsoft.Office.Interop.Word.Documents> kolekce a zadejte cestu k dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#5)]  
  
## <a name="to-open-a-document-as-read-only"></a>Chcete-li otevřít dokument jako jen pro čtení  
  
-   Volání <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> metoda, zadejte cestu k dokumentu a nastavte *jen pro čtení* argument **True** ve volání metody.  
  
     [!code-vb[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#6)]
     [!code-csharp[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#6)]  
  
## <a name="compile-the-code"></a>Kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Dokument s názvem *NewDocument.doc* musí existovat v adresáři s názvem *Test* na jednotce C.  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: Vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)   
 [Postupy: Zavírání dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-documents.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
