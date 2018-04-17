---
title: 'Postupy: otevírání sešitů prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening
- Excel [Office development in Visual Studio], opening workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a243e4972bcee77aa9d76957ab5cce289e30e120
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-open-workbooks"></a>Postupy: Otevírání sešitů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Excel.Workbooks> Kolekce v aplikaci Microsoft Office Excel je možné pracovat s všechny otevřené sešity a otevírání sešitů.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-open-an-existing-workbook"></a>Chcete-li otevřít existující sešit  
  
1.  Použití <xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A> metodu <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce, předávání v cestě k sešitu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#2)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Sešit s názvem `YourWorkbook.xls` musí existovat v adresáři s názvem `Test` na jednotky C.  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: otevírání textových souborů jako sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)   
 [Postupy: vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Postupy: ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)   
 [Postupy: zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)  
  
  