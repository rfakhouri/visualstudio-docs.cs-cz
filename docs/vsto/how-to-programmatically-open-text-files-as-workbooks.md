---
title: 'Postupy: Otevírání textových souborů jako sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 61e51f6274bc22ed0d34d33f5ff85bfbfbd927bd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812453"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Postupy: Otevírání textových souborů jako sešitů prostřednictvím kódu programu
  Jako sešit můžete otevřít textový soubor. Musíte předat název textového souboru, který chcete otevřít. Můžete zadat několik volitelných parametrů, jako je číslo řádku, které analýza kódu na začátku a sloupec formát dat v souboru.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje následující součásti:

- Oddělených čárkou textový soubor s názvem `Test.txt` , který obsahuje alespoň tři řádky textu.

- Textový soubor `Test.txt` ukládaly na jednotce c:.

## <a name="see-also"></a>Viz také:
- [Práce se sešity](../vsto/working-with-workbooks.md)
- [Postupy: Otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)
- [Postupy: Vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Postupy: Ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)
- [Postupy: Zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
