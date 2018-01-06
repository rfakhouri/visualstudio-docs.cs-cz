---
title: "Postupy: hledání textu v oblastech listů prostřednictvím kódu programu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, searching
- text [Office development in Visual Studio], searching in worksheets
- text searches, worksheets
ms.assetid: a6902711-fefb-450a-a76b-b1446d11c423
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7968fe71fffb736a6e86319339f3cc7823480403
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-search-for-text-in-worksheet-ranges"></a>Postupy: Hledání textu v oblastech listů prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Excel.Range.Find%2A> Metodu <xref:Microsoft.Office.Interop.Excel.Range> objektu umožňuje hledat text v rozsahu. Tento text může být také všechny chyby řetězců, které se mohou objevit v buňkách listů, jako například `#NULL!` nebo `#VALUE!`. Další informace o řetězce chyby najdete v tématu [hodnot v buňkách chyby](http://msdn.microsoft.com/library/office/ff839168.aspx).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Následující příklad vyhledá oblast s názvem `Fruits` a upravuje písma buněk, které obsahují slovo "jablka". Tento postup se používá také <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> metoda, která využívá dříve nastavený hledání nastavení opakování hledání. Zadejte buňky, po kterém se bude vyhledávat a <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> metoda zpracovává zbytek.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> Metody vyhledávání zabalí zpět na začátek rozsahu vyhledávání po jeho byl dosažen konec rozsahu. Váš kód musíte zajistit, že vyhledávání není obtékat kolem v nekonečné smyčce. Postup vzorku ukazuje jeden ze způsobů to postarají, pomocí <xref:Microsoft.Office.Interop.Excel.Range.Address%2A> vlastnost.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak I: použít metodu najít v doplňku Excelu?](http://go.microsoft.com/fwlink/?LinkID=130294).  
  
### <a name="to-search-for-text-in-a-worksheet-range"></a>Vyhledávání textu v listu rozsahu  
  
1.  Deklarujte proměnné pro sledování celý rozsah, první nalezen rozsah a aktuálním rozsahu nalezen.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#58)]
     [!code-vb[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#58)]  
  
2.  Vyhledejte na první shodu zadání všech parametrů s výjimkou buňky pro vyhledávání po.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#59)]
     [!code-vb[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#59)]  
  
3.  Pokračujte ve vyhledávání, dokud nejsou shody.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#60)]
     [!code-vb[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#60)]  
  
4.  Porovnání první nalezen rozsah (`firstFind`) k **nic**. Pokud `firstFind` neobsahuje žádnou hodnotu, rychle úložiště kódu nalezen rozsahu (`currentFind`).  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#61)]
     [!code-vb[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#61)]  
  
5.  Pokud adresu nalezen rozsahu odpovídá adrese první nalezen rozsahu ukončení smyčky.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#62)]
     [!code-vb[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#62)]  
  
6.  Nastavte vzhled nalezen rozsahu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#63)]
     [!code-vb[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#63)]  
  
7.  Proveďte další vyhledávání.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#64)]
     [!code-vb[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#64)]  
  
 Následující příklad ukazuje metodu dokončení.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#57)]
 [!code-vb[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#57)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s oblastmi](../vsto/working-with-ranges.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Postupy: odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  