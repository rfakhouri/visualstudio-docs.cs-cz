---
title: "Postupy: používání dialogových oken aplikace Word ve skrytém režimu prostřednictvím kódu programu | Microsoft Docs"
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
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 08427d6310421135032bb3517cda1eefc1122358
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>Postupy: Používání dialogových oken aplikace Word ve skrytém režimu prostřednictvím kódu programu
  Můžete provést komplexních operací na volání jednu metodu vyvoláním předdefinovaných dialogových oken v aplikaci Microsoft Office Word bez zobrazení je pro uživatele. Můžete to provést pomocí <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Dialog> bez volání <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> metoda.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="examples"></a>Příklady  
 Následující příklady kódu ukazují, jak používat **vzhled stránky** dialogové okno ve skrytém režimu pro nastavení více stránky vlastností instalace bez vstupu uživatele. Příklady používají <xref:Microsoft.Office.Interop.Word.Dialog> objekt, který chcete konfigurovat vlastní velikost stránky. Konkrétní nastavení pro nastavení stránky, jako je například horním okrajem, dolním okrajem a tak dále, jsou k dispozici jako pozdní vazbu vlastnosti <xref:Microsoft.Office.Interop.Word.Dialog> objektu. Tyto vlastnosti Word vytváří dynamicky za běhu.  
  
 Následující příklad ukazuje, jak k provedení této úlohy v projektech Visual Basic kde **možnost striktní** je vypnout a v projektech Visual C#, že cíl [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V těchto projektech můžete vytvořit pozdní vazba funkce v kompilátory jazyka Visual Basic a Visual C#. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]  
  
 Následující příklad ukazuje, jak k provedení této úlohy v projektech Visual Basic kde **možnost striktní** zapnutý. V těchto projektů je třeba použít pro přístup k vlastnostem pozdní vazbou reflexe. Pokud chcete použít v tomto příkladu, spusťte z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: používání předdefinovaných dialogových oken v aplikaci Word prostřednictvím kódu programu](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)   
 [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)   
 [Reflexe (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Reflexe (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  