---
title: "Postupy: otevírání stávajících dokumentů prostřednictvím kódu programu | Microsoft Docs"
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
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 151571ace6790f05c067f8dff641988301bc1b0e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-existing-documents"></a>Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> Metoda otevře existující dokument aplikace Microsoft Office Word určeného plně kvalifikovaný název a cesta k souboru. Tato metoda vrátí hodnotu <xref:Microsoft.Office.Interop.Word.Document> představující otevřenou dokumentu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-open-a-document"></a>K otevření dokumentu  
  
-   Volání <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> metodu <xref:Microsoft.Office.Interop.Word.Documents> kolekce a zadejte cestu k dokumentu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#5)]  
  
### <a name="to-open-a-document-as-read-only"></a>Chcete-li otevřít dokument jen pro čtení  
  
-   Volání <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> metoda, zadejte cestu k dokumentu a nastavit *jen pro čtení* argument **True** při volání metody.  
  
     [!code-vb[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#6)]
     [!code-csharp[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#6)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Dokument s názvem NewDocument.doc musí existovat v adresáři Test na jednotce c:.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření nových dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-documents.md)   
 [Postupy: zavírání dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-documents.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  