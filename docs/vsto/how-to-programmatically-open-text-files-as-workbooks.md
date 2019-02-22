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
ms.openlocfilehash: 8d53c21247e18f198fdac1c22a3b38c0bc5348b6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633912"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Postupy: Otevírání textových souborů jako sešitů prostřednictvím kódu programu
  Jako sešit můžete otevřít textový soubor. Musíte předat název textového souboru, který chcete otevřít. Můžete zadat několik volitelných parametrů, jako je číslo řádku, které analýza kódu na začátku a sloupec formát dat v souboru.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Příklad
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje následující součásti:

-   Oddělených čárkou textový soubor s názvem `Test.txt` , který obsahuje alespoň tři řádky textu.

-   Textový soubor `Test.txt` ukládaly na jednotce c:.

## <a name="see-also"></a>Viz také:
- [Práce se sešity](../vsto/working-with-workbooks.md)
- [Postupy: Otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)
- [Postupy: Vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Postupy: Ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)
- [Postupy: Zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
