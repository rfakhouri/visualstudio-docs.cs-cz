---
title: 'Postupy: Přesouvání listů v sešitech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 10f610513b802b2b5101bdc0c2689c3d4c5ed90b
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870529"
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>Postupy: Přesouvání listů v sešitech prostřednictvím kódu programu
  Můžete programově změnit pozici listů vzhledem k jiné listy v sešitu. Pokud nezadáte umístění pro přesunutý list, Excel vytvoří nový sešit tak, aby obsahovala ho.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-move-a-worksheet-in-a-document-level-customization"></a>Chcete-li přesunout na listu v přizpůsobení na úrovni dokumentu  
  
1.  Celkový počet listů v sešitu přiřadit proměnné a poté přesuňte první sešit tak, aby ho jako poslední.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]  
  
## <a name="to-move-a-worksheet-in-a-vsto-add-in"></a>Chcete-li přesunout na listu v doplňku VSTO  
  
1.  Celkový počet listů v sešitu přiřadit proměnné a poté přesuňte první sešit tak, aby ho jako poslední.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: Zamykání listů](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
