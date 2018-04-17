---
title: 'Postupy: Kontrola pravopisu v dokumentech prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a7445b48dc936bf57a5c93426e9ffcc7f114eb32
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>Postupy: Kontrola pravopisu v dokumentech prostřednictvím kódu programu
  Pro kontrolu pravopisu v dokumentu, použijte <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> metoda. Tato metoda vrací logickou hodnotu, která určuje, zda zadaný parametr je napsán správně.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-check-spelling-and-display-results-in-a-message-box"></a>Zkontrolujte pravopis a zobrazit výsledky v okně se zprávou  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> metoda a předejte ji na rozsah textu zkontrolujte pravopis. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: programové definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  