---
title: 'Postupy: Zamykání listů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- protection, adding to worksheets
- documents [Office development in Visual Studio], document protection
- document protection, adding to worksheets
- worksheets, protecting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7d6fb66684bd51c75e655bc2403cb6a9fb5846a2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438813"
---
# <a name="how-to-programmatically-protect-worksheets"></a>Postupy: Zamykání listů
  Funkce ochrany v aplikaci Microsoft Office Excel pomáhá zabránit uživatelům a kód v úpravách objektů v listu. Ve výchozím nastavení všechny buňky jsou zamknuté po zapnutí ochrany.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 V přizpůsobeních na úrovni dokumentu můžete chránit listů s použitím návrháře Excelu. Můžete také zamknout list prostřednictvím kódu programu za běhu v libovolným typem projektu.

> [!NOTE]
> Nelze přidat ovládací prvky Windows Forms k oblastem listu, které jsou chráněné.

## <a name="use-the-designer"></a>Pomocí návrháře

### <a name="to-protect-a-worksheet-in-the-designer"></a>K ochraně listu v Návrháři

1. V **změny** skupinu **revize** klikněte na tlačítko **Zamknout list**.

    **Zamknout list** zobrazí se dialogové okno. Můžete nastavit heslo a volitelně zadat určité akce, které uživatelé můžou provádět s listem, jako je formát buňky nebo vložit řádky.

   Můžete také povolit uživatelům upravovat konkrétní rozsahy v chráněném listů.

### <a name="to-allow-editing-in-specific-ranges"></a>Povolit úpravy v konkrétní oblasti

1. V **změny** skupinu **revize** klikněte na tlačítko **povolit uživatelům upravit oblastí**.

     **Povolit uživatelům upravit oblastí** zobrazí se dialogové okno. Můžete určit rozsahy, které jsou odemknout pomocí hesla a uživatele, kteří můžete upravit rozsahy bez hesla.

## <a name="use-code-at-runtime"></a>Použít kód za běhu
 Následující kód nastaví heslo (použitím proměnné getPasswordFromUser, který obsahuje heslo získané od uživatele) a umožňuje pouze řazení.

### <a name="to-protect-a-worksheet-by-using-code-in-a-document-level-customization"></a>K ochraně na listu s použitím kódu v přizpůsobení na úrovni dokumentu

1. Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> metoda listu. Tento příklad předpokládá, že pracujete s listem s názvem `Sheet1`.

     [!code-csharp[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#27)]

### <a name="to-protect-a-worksheet-by-using-code-in-a-vsto-add-in"></a>K ochraně na listu s použitím kódu v doplňku VSTO

1. Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Protect%2A> metoda aktivního listu.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#17)]

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: Programově odemykání listů](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)
- [Postupy: Zamykání sešitů](../vsto/how-to-programmatically-protect-workbooks.md)
- [Postupy: Skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
