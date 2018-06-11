---
title: 'Postupy: přesouvání listů v sešitech prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 45bc375a65ebc8519ec3127f67e2f31659738f33
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257797"
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>Postupy: přesouvání listů v sešitech prostřednictvím kódu programu
  Prostřednictvím kódu programu můžete změnit umístění listů relativně k jiné listy v sešitu. Pokud nezadáte umístění pro přesunutý listu, bude vytvořen nový sešit tak, aby obsahovala ho.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-move-a-worksheet-in-a-document-level-customization"></a>Přesunout na list v přizpůsobení na úrovni dokumentu  
  
1.  Celkový počet listů v sešitu přiřadit proměnné a poté přesuňte první listu, aby se stal poslední.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]  
  
## <a name="to-move-a-worksheet-in-an-vsto-add-in"></a>Chcete-li přesunout do listu v doplňku VSTO  
  
1.  Celkový počet listů v sešitu přiřadit proměnné a poté přesuňte první listu, aby se stal poslední.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Postupy: odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Postupy: zamykání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
  
  