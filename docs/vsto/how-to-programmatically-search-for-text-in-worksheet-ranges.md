---
title: 'Postupy: Hledání textu v oblastech listů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, searching
- text [Office development in Visual Studio], searching in worksheets
- text searches, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3e0befc61b39030bd7144cef10b54e70dc71e33a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419549"
---
# <a name="how-to-programmatically-search-for-text-in-worksheet-ranges"></a>Postupy: Programově hledání textu v oblastech listů
  <xref:Microsoft.Office.Interop.Excel.Range.Find%2A> Metodu <xref:Microsoft.Office.Interop.Excel.Range> objektu umožňuje hledat text v rámci rozsahu. Tento text může být také všechny chybové řetězce, které se mohou objevit v buňkách listů jako `#NULL!` nebo `#VALUE!`. Další informace o chybové řetězce, naleznete v tématu [buňky chybové hodnoty](/office/vba/excel/Concepts/Cells-and-Ranges/cell-error-values).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Následující příklad hledá oblast s názvem `Fruits` a upraví písma buněk, které obsahují slovo "apples". Tento postup také používá <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> metodu, která používá dříve hledání nastavení a opakujte hledání. Zadejte buňku, po které chcete hledat a <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> ostatní se postará metody.

> [!NOTE]
> <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> Vyhledávací metody zabalí zpět na začátek rozsahu vyhledávání, poté co dosáhne konce rozsahu. Váš kód musíte zajistit, že hledání není obtékat kolem v nekonečné smyčce. Ukázkový postup ukazuje jeden způsob, jak se o to postarají pomocí <xref:Microsoft.Office.Interop.Excel.Range.Address%2A> vlastnost.

 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Použít metodu Find v doplňku aplikace Excel? ](http://go.microsoft.com/fwlink/?LinkID=130294).

## <a name="to-search-for-text-in-a-worksheet-range"></a>K vyhledání textu v rozsahu list

1. Deklarujte proměnné pro sledování celý rozsah, první nalezené rozsahu a rozsahu aktuální nalezen.

    [!code-csharp[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#58)]
    [!code-vb[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#58)]

2. Vyhledejte první shodu, všechny parametry s výjimkou buňku vyhledávání po zadání.

    [!code-csharp[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#59)]
    [!code-vb[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#59)]

3. Pokračujte ve vyhledávání, dokud existuje shod.

    [!code-csharp[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#60)]
    [!code-vb[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#60)]

4. Porovnání první nalezené oblast (`firstFind`) k **nic**. Pokud `firstFind` neobsahuje žádnou hodnotu, úložiště kódu okamžitě nalezen rozsah (`currentFind`).

    [!code-csharp[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#61)]
    [!code-vb[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#61)]

5. Pokud adresu nalezen rozsahu odpovídá adresu první nalezené rozsahu ukončení smyčky.

    [!code-csharp[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#62)]
    [!code-vb[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#62)]

6. Nastavte vzhled oblasti nalezen.

    [!code-csharp[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#63)]
    [!code-vb[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#63)]

7. Proveďte další vyhledávání.

    [!code-csharp[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#64)]
    [!code-vb[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#64)]

   Následující příklad ukazuje kompletní metodu.

## <a name="example"></a>Příklad
 [!code-csharp[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#57)]
 [!code-vb[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#57)]

## <a name="see-also"></a>Viz také:
- [Práce s oblastmi](../vsto/working-with-ranges.md)
- [Postupy: Používání stylů pro oblasti sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)
- [Postupy: Odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
