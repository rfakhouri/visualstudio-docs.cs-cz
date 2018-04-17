---
title: 'Postupy: programové automatické naplňování oblastí s přírůstkově se měnícími daty | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e358869dea101d0c0ca012acd46b7822e6cf5873
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Postupy: Automatické naplňování oblastí s přírůstkově se měnícími daty prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> Metodu <xref:Microsoft.Office.Interop.Excel.Range> objektu umožňuje automaticky vyplnit oblast na listu s hodnotami. Nejčastěji <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metoda se používá k uložení přírůstkově zvýšení nebo snížení hodnoty v rozsahu. Můžete určit chování zadáním volitelnou konstantu z <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> výčtu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Při používání musíte zadat dva rozsahy <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   Rozsah, který volá <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metoda, která určuje počáteční bod výplně a obsahuje počáteční hodnotu.  
  
-   Rozsah, který chcete vyplnit, předá jako parametr, který se <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metoda. Tento rozsah cílových musí obsahovat rozsah, který obsahuje počáteční hodnota.  
  
    > [!NOTE]  
    >  Nelze předat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení místě <xref:Microsoft.Office.Interop.Excel.Range>. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="example"></a>Příklad  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 První buňky rozsahu, který chcete vyplnit musí obsahovat počáteční hodnotu.  
  
 Příklad vyžaduje, že vyplníte tři oblasti:  
  
-   Sloupec B je zahrnout pět dny v týdnu. Počáteční hodnota, zadejte **pondělí** v buňce B1.  
  
-   Sloupec C je zahrnout pět měsíců. Počáteční hodnota, zadejte **leden** v buňce C1.  
  
-   Sloupec D je zahrnout řady čísel, a narůstajících o dva jsou pro každý řádek. Počáteční hodnoty, zadejte **4** v buňce D1 a **6** v buňce D2.  
  
## <a name="see-also"></a>Viz také  
 [Práce s oblastmi](../vsto/working-with-ranges.md)   
 [Postupy: odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Postupy: programové používání stylů pro oblasti sešitů](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Postupy: spouštění výpočtů v aplikaci Excel](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  