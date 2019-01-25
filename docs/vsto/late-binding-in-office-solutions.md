---
title: Pozdní vazba v řešeních pro systém Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- objects [Office development in Visual Studio], casting
- types [Office development in Visual Studio], casting
- automation [Office development in Visual Studio], casting objects
- casting, object to specific type
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 520ad17bf96f4a6c657a8bd48ac0fdd29b52e1b1
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54873168"
---
# <a name="late-binding-in-office-solutions"></a>Pozdní vazba v řešeních pro systém Office
  Některé typy v objektové modely aplikací sady Office poskytují funkce, které jsou k dispozici prostřednictvím funkce pozdní vazbu. Například některé metody a vlastnosti může vrátit různé typy objektů v závislosti na kontextu aplikace Office a některé typy můžete zveřejnit různé metody nebo vlastnosti v různých kontextech.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Projekty Visual Basic where **Option Strict** je vypnuto a vizuální C# projekty, které cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] může spolupracovat přímo s typy, které využívají tyto funkce pozdní vazbu.  
  
## <a name="implicit-and-explicit-casting-of-object-return-values"></a>Implicitní a explicitní přetypování objektu návratové hodnoty  
 Mnoho metod a vlastností v aplikaci Microsoft Office, primární sestavení vzájemné spolupráce (PIA) vrátí <xref:System.Object> hodnoty, protože se může vrátit různé druhy objektů. Například <xref:Microsoft.Office.Tools.Excel.Workbook.ActiveSheet%2A> vrátí vlastnost <xref:System.Object> protože vrácená hodnota může být <xref:Microsoft.Office.Interop.Excel.Worksheet> nebo <xref:Microsoft.Office.Interop.Excel.Chart> objekt, v závislosti na tom, co je aktivní list.  
  
 Při vrácení metody nebo vlastnosti <xref:System.Object>, je nutné explicitně převést (v jazyce Visual Basic) na objekt na správný typ v projektech Visual Basicu kde **Option Strict** zapnutý. Není nutné explicitně přetypovat <xref:System.Object> návratové hodnoty v projektech Visual Basicu kde **Option Strict** je vypnuté.  
  
 Ve většině případů obsahuje referenční dokumentaci seznam možných typů návratová hodnota pro člen, který se vrátí <xref:System.Object>. Převod nebo přetypováním objektu technologie IntelliSense pro objekt v editoru kódu.  
  
 Informace o převodu v jazyce Visual Basic najdete v tématu [implicitní a explicitní převody &#40;jazyka Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions) a [funkce CType &#40;jazyka Visual Basic&#41;](/dotnet/visual-basic/language-reference/functions/ctype-function).  
  
### <a name="examples"></a>Příklady  
 Následující příklad kódu ukazuje, jak převést objekt na specifický typ v projektu jazyka Visual Basic kde **Option Strict** zapnutý. V tomto typu projektu musíte explicitně přetypovat <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Cells%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Range>. Tento příklad vyžaduje úrovni dokumentu projektu aplikace Excel s třídou list s názvem `Sheet1`.  
  
 [!code-vb[Trin_VstcoreProgramming#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/Sheet1.vb#9)]  
  
 Následující příklad kódu ukazuje, jak v projektu jazyka Visual Basic implicitně přetypován na určitý typ objektu kde **Option Strict** je ve Vizuálu nebo vypnutí C# projekt, který cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V těchto typech projektů <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Cells%2A> vlastnost je implicitně přetypován na <xref:Microsoft.Office.Interop.Excel.Range>. Tento příklad vyžaduje úrovni dokumentu projektu aplikace Excel s třídou list s názvem `Sheet1`.  
  
 [!code-vb[Trin_VstcoreProgramming#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/Sheet1.vb#10)]
 [!code-csharp[Trin_VstcoreProgramming#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/Sheet1.cs#10)]  
  
## <a name="access-members-that-are-available-only-through-late-binding"></a>Získat přístup ke členům, které jsou k dispozici pouze prostřednictvím pozdní vazby  
 Některé vlastnosti a metody v sestavení PIA sady Office jsou k dispozici pouze prostřednictvím pozdní vazbu. Projekty v jazyce Visual Basic, kde **Option Strict** je ve Vizuálu nebo vypnutí C# projekty, které cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], pozdní vazba funkce v těchto jazycích můžete použít pro přístup ke členům s pozdní vazbou. Projekty v jazyce Visual Basic, kde **Option Strict** zapnutý, je nutné použít pro přístup k těmto členům reflexe.  
  
### <a name="examples"></a>Příklady  
 Následující příklad kódu ukazuje, jak pro přístup ke členům s pozdní vazbou v projektu jazyka Visual Basic kde **Option Strict** je ve Vizuálu nebo vypnutí C# projekt, který cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V tomto příkladu přistupuje k pozdní vazbou **název** vlastnost **otevřít soubor** dialogové okno v aplikaci Word. Pokud chcete použít tento příklad, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídy v projektu aplikace Word.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 Následující příklad kódu ukazuje, jak provést stejný úkol v projektu jazyka Visual Basic pomocí reflexe kde **Option Strict** zapnutý.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>Viz také:  
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Použití typu dynamic &#40;C&#35; Průvodce programováním&#41;](/dotnet/csharp/programming-guide/types/using-type-dynamic)   
 [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Reflexe (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Reflexe (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
