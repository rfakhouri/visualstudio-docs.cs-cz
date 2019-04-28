---
title: 'Postupy: Nastavování možností hledání v aplikaci Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6e3b66bfd7f3f5d0ef0f4893efeb81c80df5d4ae
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62961872"
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>Postupy: Nastavování možností hledání v aplikaci Word
  Existují dva způsoby, jak nastavit možnosti vyhledávání pro výběr v dokumentech aplikace Microsoft Office Word:

- Nastavte jednotlivé vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu.

- Používat argumenty <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Find> objektu.

  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="use-properties-of-a-find-object"></a>Použití vlastnosti objektu Find
 Následující kód nastaví vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu Hledat text v rámci aktuálního výběru. Všimněte si, že kritéria hledání, jako je například hledání dopředu, zabalení a text pro hledání, jsou vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu.

 Nastavení jednotlivých vlastností <xref:Microsoft.Office.Interop.Word.Find> objekt není užitečné při psaní kódu jazyka C#, protože musíte zadat stejné vlastnosti jako parametry v <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metoda. Proto tento příklad obsahuje pouze kód jazyka Visual Basic.

### <a name="to-set-search-options-using-a-find-object"></a>Chcete-li nastavit možnosti hledání pomocí objektu Find

1. Nastavení vlastností <xref:Microsoft.Office.Interop.Word.Find> objekt dopředu prohledávat výběr textu **nepracuju,**.

     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]

## <a name="use-execute-method-arguments"></a>Používat argumenty Execute – metoda
 Následující kód používá <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Find> objektu Hledat text v rámci aktuálního výběru. Všimněte si, že kritéria hledání, jako je například hledání dopředu, zabalení a text pro hledání, jsou předány jako parametry <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody.

### <a name="to-set-search-options-using-execute-method-arguments"></a>Nastavení možností vyhledávání pomocí argumenty metody spouštění

1. Kritéria vyhledávání předat jako parametry <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metoda hledá směrem dopředu pomocí výběru textu **nepracuju,**.

     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]

## <a name="see-also"></a>Viz také:
- [Postupy: Programově hledání a nahrazování textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Postupy: Procházení nalezených položek v dokumentech prostřednictvím kódu programu smyčky](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
- [Postupy: Obnovení výběru po hledání prostřednictvím kódu programu](../vsto/how-to-programmatically-restore-selections-after-searches.md)
