---
title: "Postupy: Změna velikosti ovládacích prvků záložek | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- Bookmark control, resizing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: fc546ed1b840cc072510a49a16696a1bfc91cee7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-resize-bookmark-controls"></a>Postupy: Změna velikosti ovládacích prvků záložek
  Nastavení velikosti <xref:Microsoft.Office.Tools.Word.Bookmark> řízení, pokud ho přidáte do dokumentu aplikace Microsoft Office Word. Můžete taky změnit velikost ji později.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Existují tři způsoby, jak změnit velikost záložku:  
  
-   Přidat nebo odebrat textu v <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku.  
  
     Vždy, když v záložku přidat text, velikost záložky automaticky zvyšuje tak, aby obsahovala nového textu. Pokud odstraníte text, velikost záložky automaticky snižuje.  
  
-   Změna <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> a <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> vlastnosti <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku.  
  
     To je užitečné, pokud chcete změnit velikost pouze několik znaky.  
  
-   Znovu vytvořte <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku.  
  
     To je užitečné, pokud je zásadní změnu velikosti či umístění záložky.  
  
 Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky v dokumentu ve vašem projektu v době návrhu nebo za běhu. Projekty doplňku VSTO, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky pro všechny otevřené dokumenty v době běhu. Další informace najdete v tématu [postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="changing-the-start-and-end-properties"></a>Změna počátečního a koncového vlastnosti  
  
#### <a name="to-resize-a-bookmark-in-a-document-level-project-at-design-time"></a>Ke změně velikosti záložku v projektech na úrovni dokumentu v době návrhu  
  
1.  Vyberte záložku v **vlastnosti** okno.  
  
2.  Zvýšení nebo snížení hodnoty <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> vlastnost.  
  
3.  Zvýšení nebo snížení hodnoty <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> vlastnost.  
  
#### <a name="to-resize-a-bookmark-in-a-document-level-project-at-run-time"></a>Ke změně velikosti záložku v projektech na úrovni dokumentu v době běhu  
  
1.  Změnit <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> a <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> vlastnosti <xref:Microsoft.Office.Tools.Word.Bookmark> jste vytvořili v době běhu nebo v době návrhu.  
  
     Následující příklad kódu přidá na začátek záložku s názvem pět znaků `SampleBookmark`. Tento kód předpokládá, že existují alespoň 5 znaků textu před záložkou.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#2)]  
  
     Následující příklad kódu přidá na konec stejné záložku pět znaků. Tento kód předpokládá, že existují alespoň 5 znaků textu za záložkou.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#3)]  
  
#### <a name="to-resize-a-bookmark-in-an-vsto-add-in-project-at-run-time"></a>Ke změně velikosti na záložku v projektu doplňku VSTO za běhu  
  
1.  Změnit <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> a <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> vlastnosti <xref:Microsoft.Office.Tools.Word.Bookmark> jste vytvořili v době běhu.  
  
     Následující příklad kódu vytvoří <xref:Microsoft.Office.Tools.Word.Bookmark> obsahující text v prvním odstavci aktivního dokumentu a pak odebere pět znaků od začátku a konci <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     [!code-vb[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#16)]
     [!code-csharp[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#16)]  
  
## <a name="recreating-the-bookmark"></a>Nové vytvoření záložky  
 Velikost záložku v projektech na úrovni dokumentu můžete změnit tak, že přidáte novou záložku, který má stejný název jako existující záložku, ale která má různou velikost.  
  
#### <a name="to-recreate-a-bookmark-in-a-document-level-project-at-design-time"></a>Znovu vytvořte záložku v projektech na úrovni dokumentu v době návrhu  
  
1.  Vyberte text, který má být součástí nové <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku.  
  
2.  Na **vložit** nabídky, klikněte na tlačítko **záložku**.  
  
3.  V **záložku** dialogové okno, vyberte název záložky, který chcete změnit velikost a klikněte na tlačítko **přidat**.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Postupy: Změna velikosti ovládacích prvků ListObject](../vsto/how-to-resize-listobject-controls.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  