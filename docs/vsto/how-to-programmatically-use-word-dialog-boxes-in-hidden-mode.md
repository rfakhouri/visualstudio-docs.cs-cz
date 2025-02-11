---
title: 'Postupy: Používání dialogových oken aplikace Word ve skrytém režimu prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e7a422e9548fabefa2066fb439c01e382586cd36
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62961602"
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>Postupy: Používání dialogových oken aplikace Word ve skrytém režimu prostřednictvím kódu programu
  Vyvoláním předdefinovaných dialogových oken v aplikaci Microsoft Office Word bez zobrazení uživateli můžete provádět komplexní operace s jedné metody volání. Můžete to provést pomocí <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Dialog> objektu bez volání <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> metoda.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="examples"></a>Příklady
 Následující příklady kódu ukazují, jak používat **vzhled stránky** dialogové okno ve skrytém režimu můžete nastavit více stránek vlastnosti instalaci bez vstupu uživatele. V příkladech se používá <xref:Microsoft.Office.Interop.Word.Dialog> objektu, který chcete konfigurovat vlastní velikost stránky. Specifické nastavení pro vzhled stránky, jako je například horní okraj, dolní okraj a tak dále, jsou k dispozici jako vlastnosti s pozdní vazbou <xref:Microsoft.Office.Interop.Word.Dialog> objektu. Tyto vlastnosti jsou dynamicky vytvořené aplikace Word v době běhu.

 Následující příklad ukazuje, jak k provedení této úlohy v projektech Visual Basicu kde **Option Strict** je vypnout a v projektech Visual C#, které se zaměřují [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V těchto projektech můžete pozdní vazba funkce v kompilátorech jazyka Visual Basic a Visual C#. Pokud chcete použít tento příklad, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídu ve vašem projektu.

 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]

 Následující příklad ukazuje, jak k provedení této úlohy v projektech Visual Basicu kde **Option Strict** zapnutý. V těchto projektech je nutné použít reflexe pro přístup k vlastnosti s pozdní vazbou. Pokud chcete použít tento příklad, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídu ve vašem projektu.

 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]

## <a name="see-also"></a>Viz také:
- [Postupy: Používání předdefinovaných dialogových oken v aplikaci Word prostřednictvím kódu programu](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)
- [Přehled modelu objektů aplikace Word](../vsto/word-object-model-overview.md)
- [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)
- [Reflexe (C#)](/dotnet/csharp/programming-guide/concepts/reflection)
- [Reflexe (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)
