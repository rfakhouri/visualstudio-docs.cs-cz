---
title: "Postupy: zamykání listů prostřednictvím kódu programu | Microsoft Docs"
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
- protection, adding to worksheets
- documents [Office development in Visual Studio], document protection
- document protection, adding to worksheets
- worksheets, protecting
ms.assetid: 50bde1ff-918a-42ca-ba1b-f22139f8717a
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f653ef0157ed0060066e3aa3ea923794854450d3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-protect-worksheets"></a>Postupy: Zamykání listů prostřednictvím kódu programu
  Funkce ochrany v aplikaci Microsoft Office Excel pomáhá zabránit uživatelům a kód upravování objektů v listu. Standardně jsou všechny buňky zamčené po zapnutí ochrany.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 V přizpůsobeních na úrovni dokumentu můžete chránit listů pomocí návrháře aplikace Excel. Můžete taky chránit list prostřednictvím kódu programu za běhu v libovolného typu projektu.  
  
> [!NOTE]  
>  Ovládací prvky Windows Forms nelze přidat do oblasti listu, které jsou chráněné.  
  
## <a name="using-the-designer"></a>Pomocí návrháře  
  
#### <a name="to-protect-a-worksheet-in-the-designer"></a>K ochraně listu v Návrháři  
  
1.  V **změny** u **zkontrolujte** , klikněte na **Zamknout list**.  
  
     **Zamknout list** zobrazí se dialogové okno. Můžete nastavit heslo a volitelně určete určité akce, které můžou uživatelé provést s listu, jako je například formát buněk nebo vložit řádky.  
  
 Můžete také povolit uživatelům upravit konkrétní oblasti v listech chráněný.  
  
#### <a name="to-allow-editing-in-specific-ranges"></a>Povolit úpravy v konkrétních oblastech  
  
1.  V **změny** u **zkontrolujte** , klikněte na **povolit uživatelům upravit oblastí**.  
  
     **Povolit uživatelům upravit oblastí** zobrazí se dialogové okno. Můžete zadat rozsahy, které jsou odemknout pomocí hesla a uživatelé, kteří mohou upravovat rozsahy bez zadání hesla.  
  
## <a name="using-code-at-run-time"></a>Pomocí kódu v době běhu  
 Následující kód nastaví heslo (pomocí proměnné getPasswordFromUser, který obsahuje heslo získaný od uživatele) a umožňuje pouze řazení.  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-document-level-customization"></a>K ochraně na listu s použitím kódu v přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> metoda listu. Tento příklad předpokládá, že pracujete s na listu s názvem `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#27)]  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-vsto-add-in"></a>K ochraně na listu s použitím kódu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Protect%2A> metoda aktivního listu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#17)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: programové odemykání listů](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)   
 [Postupy: zamykání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-protect-workbooks.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  