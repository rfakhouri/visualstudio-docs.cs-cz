---
title: 'Postupy: Zavírání dokumentů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing
- Word [Office development in Visual Studio], closing documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 504fe863c746a788e797d3a84c4cd0b3d6c3d19b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63422475"
---
# <a name="how-to-programmatically-close-documents"></a>Postupy: Zavírání dokumentů prostřednictvím kódu programu
  Můžete zavřít aktivní dokument nebo můžete zadat dokument zavřít.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="close-the-active-document"></a>Zavřít aktivní dokument
 Existují dva postupy pro zavření aktivního dokumentu: jeden pro přizpůsobení na úrovni dokumentu a jeden pro doplňky VSTO.

### <a name="to-close-the-active-document-in-a-document-level-customization"></a>Zavřít aktivní dokument v přizpůsobení na úrovni dokumentu

1. Volání <xref:Microsoft.Office.Tools.Word.Document.Close%2A> metodu `ThisDocument` třídu ve vašem projektu zavřete dokument přidružený k přizpůsobení. Pokud chcete použít následující příklad kódu, spusťte jej z `ThisDocument` třídy.

    > [!NOTE]
    > Tento příklad předává <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> hodnota, která se *SaveChanges* parametr okno zavřít bez uložení změn nebo výzvy pro uživatele.

     [!code-vb[Trin_VstcoreWordAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#3)]
     [!code-csharp[Trin_VstcoreWordAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#3)]

### <a name="to-close-the-active-document-in-a-vsto-add-in"></a>Zavření aktivního dokumentu v doplňku VSTO

1. Volání <xref:Microsoft.Office.Interop.Word._Document.Close%2A> metodu <xref:Microsoft.Office.Interop.Word._Application.ActiveDocument%2A> vlastnost zavřít aktivní dokument. Pokud chcete použít následující příklad kódu, spusťte jej z `ThisAddIn` třídu ve vašem projektu.

    > [!NOTE]
    > Tento příklad předává <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> hodnota, která se *SaveChanges* parametr okno zavřít bez uložení změn nebo výzvy pro uživatele.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#3)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#3](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#3)]

## <a name="close-a-document-that-you-specify-by-name"></a>Zavření dokumentu, který určíte podle názvu
 Způsob, jakým zavření dokumentu, který určíte podle názvu je stejný pro přizpůsobení na úrovni dokumentu a doplňky VSTO.

### <a name="to-close-a-document-that-you-specify-by-name"></a>Chcete-li zavřít dokument, který určíte podle názvu

1. Zadejte název dokumentu jako argument <xref:Microsoft.Office.Interop.Word._Application.Documents%2A> kolekci a poté zavolejte <xref:Microsoft.Office.Interop.Word._Document.Close%2A> metoda. Následující příklad kódu předpokládá, že dokument s názvem **NewDocument** je otevřen v aplikaci Word.

    > [!NOTE]
    > Tento příklad předává <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> hodnota, která se *SaveChanges* parametr okno zavřít bez uložení změn nebo výzvy pro uživatele.

     [!code-vb[Trin_VstcoreWordAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#4)]
     [!code-csharp[Trin_VstcoreWordAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#4)]

## <a name="see-also"></a>Viz také:
- [Postupy: Otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)
- [Postupy: Ukládání dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-documents.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
