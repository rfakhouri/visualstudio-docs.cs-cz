---
title: 'Postupy: otevírání textových souborů jako sešitů prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cafe64ce693972bd9c254a6bdfc1dcbf70f004c9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Postupy: Otevírání textových souborů jako sešitů prostřednictvím kódu programu
  Jako sešit můžete otevřít textového souboru. Je nutné předat název textového souboru, který chcete otevřít. Můžete zadat několik volitelné parametry, jako je například číslo řádku, které a spustit analýzu na sloupec formát data v souboru.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje následující součásti:  
  
-   Text oddělený čárkami soubor s názvem `Test.txt` , který obsahuje alespoň tři řádky textu.  
  
-   Textový soubor `Test.txt` ukládaly na jednotce c:.  
  
## <a name="see-also"></a>Viz také  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)   
 [Postupy: vytváření nových sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Postupy: ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)   
 [Postupy: zavírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-workbooks.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  