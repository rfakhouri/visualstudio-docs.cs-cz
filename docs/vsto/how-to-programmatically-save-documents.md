---
title: 'Postupy: Ukládání dokumentů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b4fbf8e4cb67d5216dc17c325911bb243fae6e1c
ms.sourcegitcommit: 5b34052a1c7d86179d7898ed532babb2d9dad4a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490609"
---
# <a name="how-to-programmatically-save-documents"></a>Postupy: Ukládání dokumentů prostřednictvím kódu programu

Existuje několik způsobů, jak uložit systém Microsoft Office dokumentů aplikace Word. Dokument můžete uložit beze změny názvu dokumentu, nebo můžete dokument uložit s novým názvem.

[!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="save-a-document-without-changing-the-name"></a>Uložení dokumentu beze změny názvu

### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>Uložení dokumentu přidruženého k přizpůsobení na úrovni dokumentu

1. <xref:Microsoft.Office.Tools.Word.Document.Save%2A> Zavolejte metodu<xref:Microsoft.Office.Tools.Word.Document> třídy. Chcete-li použít tento příklad kódu, spusťte jej `ThisDocument` z třídy v projektu.

     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]

### <a name="to-save-the-active-document"></a>Uložení aktivního dokumentu

1. <xref:Microsoft.Office.Interop.Word._Document.Save%2A> Zavolejte metodu pro aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej `ThisDocument` z `ThisAddIn` třídy nebo v projektu.

    [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
    [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]

   Pokud si nejste jistí, jestli je dokument, který chcete uložit, v aktivním dokumentu, můžete na něj odkazovat podle jeho názvu.

### <a name="to-save-a-document-specified-by-name"></a>Uložení dokumentu určeného názvem

1. Použijte název dokumentu jako argument pro <xref:Microsoft.Office.Interop.Word.Documents> kolekci. Chcete-li použít tento příklad kódu, spusťte jej `ThisDocument` z `ThisAddIn` třídy nebo v projektu.

     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]

## <a name="save-a-document-with-a-new-name"></a>Uložení dokumentu s novým názvem

`SaveAs` Použijte metodu k uložení dokumentu s novým názvem. Tuto metodu <xref:Microsoft.Office.Tools.Word.Document> lze použít pro položku hostitele v projektu aplikace na úrovni dokumentu nebo na nativní <xref:Microsoft.Office.Interop.Word.Document> objekt v jakémkoli projektu aplikace Word. Tato metoda vyžaduje, abyste zadali nový název souboru, ale jiné argumenty jsou volitelné.

> [!NOTE]
> Pokud zobrazíte dialogové **okno SaveAs** <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> uvnitř obslužné `ThisDocument` rutiny události a nastavíte parametr *Cancel* na **hodnotu false**, aplikace může být neočekávaně ukončena. Pokud nastavíte parametr *Cancel* na **hodnotu true**, zobrazí se chybová zpráva oznamující, že automatické ukládání bylo zakázané.

### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>Uložení dokumentu přidruženého k přizpůsobení na úrovni dokumentu s novým názvem

1. `SaveAs` Zavolejte metodu `ThisDocument` třídy v projektu pomocí plně kvalifikované cesty a názvu souboru. Pokud soubor s tímto názvem již v této složce existuje, je tiše přepsán. Chcete-li použít tento příklad kódu, spusťte jej `ThisDocument` z třídy.

    > [!NOTE]
    > `SaveAs` Metoda vyvolá výjimku, pokud cílový adresář neexistuje nebo pokud existují jiné problémy při ukládání souboru. Je dobrým zvykem použít`try...catch` blok `SaveAs` kolem metody nebo uvnitř metody volání.

     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]

### <a name="to-save-a-native-document-with-a-new-name"></a>Uložení nativního dokumentu s novým názvem

1. <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> Zavolejte metodu <xref:Microsoft.Office.Interop.Word.Document> , kterou chcete uložit, pomocí plně kvalifikované cesty a názvu souboru. Pokud soubor s tímto názvem již v této složce existuje, je tiše přepsán.

     Následující příklad kódu uloží aktivní dokument s novým názvem. Chcete-li použít tento příklad kódu, spusťte jej `ThisDocument` z `ThisAddIn` třídy nebo v projektu.

    > [!NOTE]
    > <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> Metoda vyvolá výjimku, pokud cílový adresář neexistuje nebo pokud existují jiné problémy při ukládání souboru. Je vhodné použít **testovaný postup...** Zachyťte blok <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> kolem metody nebo uvnitř metody volání.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]

## <a name="compile-the-code"></a>Kompilace kódu

Tento příklad kódu vyžaduje následující:

- Chcete-li uložit dokument podle názvu, musí existovat dokument s názvem *NewDocument. doc* v adresáři s názvem *test* na jednotce C.

- Chcete-li uložit dokument s novým názvem, musí existovat adresář s názvem *test* na jednotce C.

## <a name="see-also"></a>Viz také:

- [Postupy: Programové zavření dokumentů](../vsto/how-to-programmatically-close-documents.md)
- [Postupy: Programové otevření existujících dokumentů](../vsto/how-to-programmatically-open-existing-documents.md)
- [Položka hostitele dokumentu](../vsto/document-host-item.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
