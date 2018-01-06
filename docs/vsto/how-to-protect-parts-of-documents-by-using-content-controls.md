---
title: "Postupy: ochrana částí dokumentů pomocí ovládacích prvků obsahu | Microsoft Docs"
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
- restricted permissions [Office development in Visual Studio]
- partial document protection [Office development in Visual Studio]
- content controls [Office development in Visual Studio], protecting documents
- Word [Office development in Visual Studio], partial document protection
- document protection [Office development in Visual Studio]
- Word [Office development in Visual Studio], restricted permissions
- GroupContentControl
ms.assetid: 50d7286a-7746-446f-8eef-06ceeadc94d0
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 894379e107865e4a4d187c963a88fe23b6eec6d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-protect-parts-of-documents-by-using-content-controls"></a>Postupy: Ochrana částí dokumentů pomocí ovládacích prvků obsahu
  Když chráníte část dokumentu, můžete zabránit uživatelům ve měnit nebo odstraňovat obsah v této části dokumentu. Části dokumentu aplikace Microsoft Office Word můžete chránit pomocí ovládacích prvků obsahu několika způsoby:  
  
-   Můžete chránit obsah ovládacího prvku.  
  
-   Můžete chránit část dokumentu, který není v prvku obsahu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
##  <a name="EditDeleteControl"></a>Ochrana obsahu ovládacího prvku  
 Můžete zabránit uživatelům v úpravy nebo odstranění obsahu ovládacího prvku nastavením vlastností ovládacího prvku v projektech na úrovni dokumentu v době návrhu nebo za běhu.  
  
 Můžete taky chránit ovládací prvky obsahu, které můžete přidat do dokumentu za běhu pomocí projektu doplňku VSTO. Další informace najdete v tématu [postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
#### <a name="to-protect-a-content-control-at-design-time"></a>K ochraně obsahu ovládacího prvku v době návrhu  
  
1.  V dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, vyberte ovládací prvek obsahu, který chcete chránit.  
  
2.  V **vlastnosti** nastavte jedno nebo obě z následujících vlastností:  
  
    -   Chcete-li zabránit uživatelům v úpravy ovládacího prvku, nastavte **LockContents** k **True**.  
  
    -   Chcete-li zabránit uživatelům v odstranění ovládacího prvku, nastavte **LockContentControl** k **True**.  
  
3.  Click **OK**.  
  
#### <a name="to-protect-a-content-control-at-run-time"></a>K ochraně obsahu ovládacího prvku za běhu  
  
1.  Nastavit `LockContents` vlastnost obsah ovládacího prvku na **true** uživatelům zabránit ovládacím prvku pro úpravy, a nastavte `LockContentControl` vlastnost **true** uživatelům zabránit v odstranění ovládacího prvku.  
  
     Následující příklad kódu ukazuje, jak pomocí <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> a <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> dva různé vlastnosti <xref:Microsoft.Office.Tools.Word.RichTextContentControl> objekty v projektech na úrovni dokumentu. Pokud chcete spustit tento kód, přidejte kód, který `ThisDocument` třídy v projektu a volání `AddProtectedContentControls` metoda z `ThisDocument_Startup` obslužné rutiny události.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#2)]  
  
     Následující příklad kódu ukazuje, jak pomocí <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> a <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> dva různé vlastnosti <xref:Microsoft.Office.Tools.Word.RichTextContentControl> objekty v projektu doplňku VSTO. Pokud chcete spustit tento kód, přidejte kód, který `ThisAddIn` třídy v projektu a volání `AddProtectedContentControls` metoda z `ThisAddIn_Startup` obslužné rutiny události.  
  
     [!code-vb[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#14)]
     [!code-csharp[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#14)]  
  
## <a name="protecting-a-part-of-a-document-that-is-not-in-a-content-control"></a>Ochrana část dokumentu, který není v prvku obsahu  
 Vám může zabránit uživatelům v změna oblast dokumentu umístěním oblasti <xref:Microsoft.Office.Tools.Word.GroupContentControl>. To je užitečné v následujících scénářích:  
  
-   Chcete chránit oblast, která neobsahuje ovládací prvky obsahu.  
  
-   Chcete chránit oblast, která již obsahuje ovládací prvky obsahu, ale text nebo další položky, které chcete chránit, nejsou v ovládacích prvků obsahu.  
  
> [!NOTE]  
>  Pokud vytvoříte <xref:Microsoft.Office.Tools.Word.GroupContentControl> obsahující vložený ovládací prvky obsahu, vložené ovládací prvky obsahu nejsou chráněna automaticky. Chcete-li zabránit uživatelům v úpravy vloženému ovládacímu prvku obsahu, použijte **LockContents** vlastností ovládacího prvku.  
  
#### <a name="to-protect-an-area-of-a-document-at-design-time"></a>K ochraně oblast dokumentu v době návrhu  
  
1.  V dokumentu, který je hostován v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, vyberte oblast, na který chcete chránit.  
  
2.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  V **ovládací prvky** klikněte na možnost **skupiny** tlačítko rozevíracího seznamu a pak klikněte na tlačítko **skupiny**.  
  
     A <xref:Microsoft.Office.Tools.Word.GroupContentControl> obsahující chráněného oblast je automaticky generován v `ThisDocument` třídy ve vašem projektu. Ohraničení, představující ovládací prvek skupiny je viditelný v době návrhu, ale není k dispozici žádné viditelné ohraničení za běhu.  
  
#### <a name="to-protect-an-area-of-a-document-at-run-time"></a>K ochraně oblast dokumentu za běhu  
  
1.  Prostřednictvím kódu programu vyberte oblast, na který chcete chránit a pak zavolají <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> metodu pro vytvoření <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
     Následující příklad kódu pro projekt na úrovni dokumentu a přidá vybere prvním odstavci text, který má první odstavce do dokumentu a poté vytvoří <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Pokud chcete spustit tento kód, přidejte kód, který `ThisDocument` třídy v projektu a volání `ProtectFirstParagraph` metoda z `ThisDocument_Startup` obslužné rutiny události.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#1)]  
  
     Následující příklad kódu pro projektu doplňku VSTO přidá text na prvním odstavci v aktivním dokumentu, vybere prvním odstavci a poté se vytvoří instance <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Pokud chcete spustit tento kód, přidejte kód, který `ThisAddIn` třídy v projektu a volání `ProtectFirstParagraph` metoda z `ThisAddIn_Startup` obslužné rutiny události.  
  
     [!code-vb[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#15)]
     [!code-csharp[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#15)]  
  
## <a name="see-also"></a>Viz také  
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Ovládací prvky obsahu](../vsto/content-controls.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)  
   