---
title: "BOOKMARK – ovládací prvek | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 38e3286d24f0591ca4ced3339118b6d0d4bfe1d7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="bookmark-control"></a>Záložka – ovládací prvek
  <xref:Microsoft.Office.Tools.Word.Bookmark> Řízení je záložku, na kterou má jedinečný název, zpřístupní události a mohou být vázány na data. Záložka slouží jako zástupný znak označit položku nebo místo v dokumentu aplikace Microsoft Office Word. <xref:Microsoft.Office.Tools.Word.Bookmark> Ovládací prvek je kombinací <xref:Microsoft.Office.Interop.Word.Bookmark> objektu a <xref:Microsoft.Office.Interop.Word.Range> objektu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacích prvků do dokumentu v době návrhu nebo za běhu. Projekty doplňku VSTO, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky pro všechny otevřené dokumenty v době běhu. Další informace najdete v tématu [postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
## <a name="binding-data-to-the-control"></a>Vazba dat k ovládacímu prvku  
 A <xref:Microsoft.Office.Tools.Word.Bookmark> řízení podporuje jednoduché datové vazby. Záložka by měla být vázána na zdroje dat pomocí <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> vlastnost. Je výchozí vlastnost vazby dat záložky <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> vlastnost.  
  
 Při aktualizaci dat v datové sadě vázané <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek odráží změny.  
  
 V projektech na úrovni dokumentu, můžete také vázat data na záložky pomocí **zdroje dat** okno. Další informace najdete v tématu [postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
## <a name="formatting"></a>Formátování  
 Formátování, které lze použít pro <xref:Microsoft.Office.Interop.Word.Bookmark> lze použít pro <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku. To zahrnuje písma, odsazení, mezery, číslování a styly.  
  
## <a name="assigning-text-to-the-bookmark"></a>Přiřazení Text na záložku  
 Další rozdíl mezi <xref:Microsoft.Office.Interop.Word.Bookmark> objektu a <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek je, jak se chová při přiřazení text na záložku. Pokud přiřadíte textu nulovou délkou <xref:Microsoft.Office.Interop.Word.Bookmark>, se připojí text doprava záložky a Záložka zůstane nulové délky. Ale pokud přiřadíte textu nulovou délkou <xref:Microsoft.Office.Tools.Word.Bookmark>, text je vložen do záložky a délka záložku zasahuje do celkový počet znaků, vložit.  
  
 <xref:Microsoft.Office.Tools.Word.Bookmark> Řízení má také <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> vlastnost. To se liší od <xref:Microsoft.Office.Interop.Word.Range.Text%2A> vlastnost, která je k dispozici na <xref:Microsoft.Office.Tools.Word.Bookmark.Range%2A> vlastnost <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvek nebo <xref:Microsoft.Office.Interop.Word.Bookmark.Range%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Bookmark> objektu.  
  
|Text – vlastnost|Popis|  
|-------------------|-----------------|  
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A>|Pomocí této vlastnosti můžete zobrazit text v záložce a nechte záložku v dokumentu. Přiřazení text na záložku rozšíří rozsah záložku a nedojde k odstranění záložky.<br /><br /> Například `Bookmark1.Text = "Hello world"` vloží text do záložky a neporušené záložky.|  
|<xref:Microsoft.Office.Interop.Word.Range.Text%2A>|Pomocí této vlastnosti můžete zobrazit text v umístění záložku a automaticky odstraní záložky. Například `Bookmark1.Range.Text = "Hello world"` vloží text do záložky a odstraní záložky.|  
  
## <a name="renaming-the-control-at-design-time"></a>Přejmenování ovládacího prvku v době návrhu  
 V projektech na úrovni dokumentu, při přetažení <xref:Microsoft.Office.Tools.Word.Bookmark> řídit z **sada nástrojů** do dokumentu sady Visual Studio automaticky vygeneruje název ovládacího prvku. Můžete změnit název ovládacího prvku **vlastnosti** okno.  
  
## <a name="overlapping-controls"></a>Překrývající se ovládací prvky  
 Ovládacích prvků záložek může dojít k překrytí vzájemně; To znamená aby se stejný text může být sdílen více než jeden záložky. Přiřadíte-li nový text do jednoho z překrývající se záložky, bude obsahovat pouze nového textu a záložky se už překrývat. Další záložku bude teď obsahovat pouze text, který nebyl sdílen mezi původní překrývající se záložky.  
  
 Následující tabulka ukazuje, jak se věta "Toto je ukázkový text". je sdílen dvě překrývající se záložky.  
  
|Záložka|Text|  
|--------------|----------|  
|Překrývající se záložky|[Toto je ukázkový {] text.}|  
|Bookmark1|Zde je ukázka|  
|Bookmark2|Ukázkový text.|  
  
 Chcete-li přiřadit nový text "To náhrada není dostupná." Chcete-li Bookmark1 už překrývající se záložky a Bookmark2 zachová pouze text, který původně nebyla součástí Bookmark1.  
  
|Záložka|Text|  
|--------------|----------|  
|Dva samostatné záložky|[Toto je nahrazení] {text}.|  
|Bookmark1|Toto je nahrazení|  
|Bookmark2|text.|  
  
 Pokud jeden záložku je plně obsažen v rámci jiné záložku a změňte text vnější záložky, vnitřní záložka se neodstraní. Ale vnitřní záložka se změní na prázdný záložku, který je přesunout na konec vnější záložky. Následující tabulka ukazuje, jak se věta "Toto je ukázkový text". je sdílen záložku, který je obsažený v jiné záložky.  
  
|Záložka|Text|  
|--------------|----------|  
|Překrývající se záložky|[Toto je text {ukázka}].|  
|Bookmark1|Toto je ukázkový text.|  
|Bookmark2|ukázka|  
  
 Chcete-li přiřadit nový text "To náhrada není dostupná." Pokud chcete Bookmark1 už překrývající se záložky a Bookmark2 se změní na prázdný záložku, který se nachází na konci Bookmark1.  
  
|Záložka|Text|  
|--------------|----------|  
|Dva samostatné záložky|[Toto je nahrazení.] {}|  
|Bookmark1|Toto je nahrazení.|  
|Bookmark2|*\<Prázdný >*|  
  
## <a name="events"></a>Události  
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>  
  
## <a name="see-also"></a>Viz také  
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Návod: Vytváření místních nabídek pro záložky](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  