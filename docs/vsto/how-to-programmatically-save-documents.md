---
title: "Postupy: ukládání dokumentů prostřednictvím kódu programu | Microsoft Docs"
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
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
ms.assetid: a6225ae9-94f5-421a-9860-5299002d543d
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 251522a745ee7b8dc9894a403f09d1a6d3f32793
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-save-documents"></a>Postupy: Ukládání dokumentů prostřednictvím kódu programu
  Existuje několik způsobů pro uložení dokumentů Microsoft Office Word. Dokument lze uložit bez úpravy názvu dokumentu nebo můžete uložit dokument pod novým názvem.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="saving-a-document-without-changing-the-name"></a>Uložení dokumentu bez úpravy názvu  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>Uložte dokument přidružený k přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.Save%2A> metodu <xref:Microsoft.Office.Tools.Word.Document> třídy. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]  
  
#### <a name="to-save-the-active-document"></a>Uložení aktivního dokumentu  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.Save%2A> metodu pro aktivní dokument. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
     [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]  
  
 Pokud si nejste jisti, jestli je dokument, který chcete uložit aktivní dokument, je můžete na něj odkazovat pomocí jeho názvu.  
  
#### <a name="to-save-a-document-specified-by-name"></a>Uložte dokument zadaný podle názvu  
  
1.  Použít jako argument pro název dokumentu <xref:Microsoft.Office.Interop.Word.Documents> kolekce. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]  
  
## <a name="saving-a-document-with-a-new-name"></a>Ukládání dokument pod novým názvem.  
 Pomocí této metody uložit jako s novým názvem uložit dokument. Můžete použít tuto metodu <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka v projektech na úrovni dokumentů aplikace Word, nebo nativní <xref:Microsoft.Office.Interop.Word.Document> objektu v jakékoli projektu aplikace Word. Tato metoda vyžaduje, aby zadejte nový název souboru, ale další argumenty jsou volitelné.  
  
> [!NOTE]  
>  Pokud můžete zobrazit **uložit jako** dialogové okno uvnitř <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> obslužné rutiny události z `ThisDocument` a nastavte *zrušit* parametru **false**, může aplikace neočekávaně ukončí. Pokud nastavíte *zrušit* parametru **true**, zobrazí chybová zpráva, která určuje, že bylo zakázáno automatické ukládání.  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>Uložení dokumentu přidružené přizpůsobení na úrovni dokumentu s novým názvem  
  
1.  Volání <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> metodu `ThisDocument` třídy ve vašem projektu pomocí plně kvalifikovaný název a cesta k souboru. Pokud soubor s tímto názvem již existuje v této složce, je bezobslužně přepsána. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` třídy.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> Metoda vyvolá výjimku, pokud cílový adresář neexistuje nebo pokud se objeví jiné problémy ukládání souboru. Je vhodné používat **try... catch** blokovat kolem <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> metoda nebo uvnitř volání metody.  
  
     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]  
  
#### <a name="to-save-a-native-document-with-a-new-name"></a>Uložit nativní dokument pod novým názvem.  
  
1.  Volání <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> , kterou chcete uložit, pomocí plně kvalifikovaný název a cesta k souboru. Pokud soubor s tímto názvem již existuje v této složce, je bezobslužně přepsána.  
  
     Následující příklad kódu uloží aktivní dokument pod novým názvem. Chcete-li použít tento příklad kódu, spusťte jej z `ThisDocument` nebo `ThisAddIn` třídy ve vašem projektu.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> Metoda vyvolá výjimku, pokud cílový adresář neexistuje nebo pokud se objeví jiné problémy ukládání souboru. Je vhodné používat **try... catch** blokovat kolem <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> metoda nebo uvnitř volání metody.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Uložte dokument podle názvu, dokument s názvem NewDocument.doc musí existovat v adresáři Test na jednotce c:.  
  
-   Uložte dokument pod novým názvem, musí existovat adresář s názvem Test na jednotce c:.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: zavírání dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-close-documents.md)   
 [Postupy: otevírání stávajících dokumentů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Hostitelská položka Document](../vsto/document-host-item.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  