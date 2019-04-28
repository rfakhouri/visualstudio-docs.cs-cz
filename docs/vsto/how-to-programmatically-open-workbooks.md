---
title: 'Postupy: Otevírání sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening
- Excel [Office development in Visual Studio], opening workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: facf3cbeb6635324e74244983fcb33138ad64cfe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812371"
---
# <a name="how-to-programmatically-open-workbooks"></a>Postupy: Otevírání sešitů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Excel.Workbooks> Kolekce v aplikaci Microsoft Office Excel je možné pracovat s všechny sešity a otevírání sešitů.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-open-an-existing-workbook"></a>Otevřete existující sešit

1. Použití <xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A> metodu <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce předávání v cestě k sešitu.

     [!code-csharp[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#2)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad kódu vyžaduje následující:

- Sešit s názvem `YourWorkbook.xls` musí existovat v adresáři s názvem `Test` na jednotce C.

## <a name="see-also"></a>Viz také:
- [Práce se sešity](../vsto/working-with-workbooks.md)
- [Postupy: Otevírání textových souborů jako sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)
- [Postupy: Vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Postupy: Ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)
- [Postupy: Zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
