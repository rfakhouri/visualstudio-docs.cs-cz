---
title: 'Postupy: Kontrola pravopisu v dokumentech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 26eb7e0798fbcf6aad33dd45892a23fb0d54b812
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62575699"
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>Postupy: Kontrola pravopisu v dokumentech prostřednictvím kódu programu
  Pokud chcete zkontrolovat pravopis v dokumentu, použijte <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> metody. Tato metoda vrátí logickou hodnotu, která určuje, zda je zadaný parametr napsaný správně.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-check-spelling-and-display-results-in-a-message-box"></a>Kontrola pravopisu a zobrazit výsledky v okně se zprávou

1. Volání <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> metoda a předat ji celou řadu text, který má zkontrolovat pravopis. Pokud chcete použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově definování a výběr oblastí v dokumentech](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
