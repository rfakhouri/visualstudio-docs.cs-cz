---
title: 'Postupy: používání předdefinovaných dialogových oken v aplikaci Word prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 80406a8048529f811cf9cbeadc8d185577a114f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>Postupy: Používání předdefinovaných dialogových oken v aplikaci Word prostřednictvím kódu programu
  Při práci s Microsoft Office Word, jsou časy, kdy je třeba zobrazit dialogová okna pro vstup uživatele. I když můžete vytvořit vlastní, můžete také chtít postup používání předdefinovaných dialogových oken v aplikaci Word, které jsou přístupné <xref:Microsoft.Office.Interop.Word.Dialogs> kolekce <xref:Microsoft.Office.Interop.Word.Application> objektu. To umožňuje přístup k více než 200 předdefinovaných dialogových oken, které jsou reprezentovány jako výčty.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="displaying-dialog-boxes"></a>Zobrazování dialogových oken  
 Chcete-li zobrazit dialogové okno, použijte jednu z hodnot <xref:Microsoft.Office.Interop.Word.WdWordDialog> výčtu k vytvoření <xref:Microsoft.Office.Interop.Word.Dialog> objekt, který reprezentuje dialogových oken, která se má zobrazit. Potom zavolejte <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> metodu <xref:Microsoft.Office.Interop.Word.Dialog> objektu.  
  
 Následující příklad kódu ukazuje, jak zobrazit **otevřít soubor** dialogové okno. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]  
  
### <a name="accessing-dialog-box-members-that-are-available-through-late-binding"></a>Přístup ke členům pole dialogové okno, které jsou k dispozici prostřednictvím pozdní vazba  
 Některé vlastnosti a metody dialogových oken v aplikaci Word jsou k dispozici pouze prostřednictvím pozdní vazbu. V jazyce Visual Basic projekty kde **možnost striktní** zapnutý, reflexe musí používat pro přístup tito členové. Další informace najdete v tématu [pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md).  
  
 Následující příklad kódu ukazuje, jak používat **název** vlastnost **otevřít soubor** dialogové okno v jazyce Visual Basic, projekty, kde **možnost striktní** vypnutý nebo v jazyce Visual C# projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 Následující příklad kódu ukazuje, jak používat pro přístup k reflexe **název** vlastnost **otevřít soubor** dialogové okno v jazyce Visual Basic, projekty, kde **možnost striktní** je na. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: používání dialogových oken aplikace Word ve skrytém režimu prostřednictvím kódu programu](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Reflexe (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Reflexe (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  