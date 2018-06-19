---
title: Bookmark – ovládací prvek
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 60ab9db37f3ed41de4afcdecbf2c9e83ffb5c2f6
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264009"
---
# <a name="bookmark-control"></a>Bookmark – ovládací prvek
  <xref:Microsoft.Office.Tools.Word.Bookmark> Řízení je záložku, na kterou má jedinečný název, zpřístupní události a mohou být vázány na data. Záložka slouží jako zástupný znak označit položku nebo místo v dokumentu aplikace Microsoft Office Word. <xref:Microsoft.Office.Tools.Word.Bookmark> Ovládací prvek je kombinací <xref:Microsoft.Office.Interop.Word.Bookmark> objektu a <xref:Microsoft.Office.Interop.Word.Range> objektu.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacích prvků do dokumentu v době návrhu nebo za běhu. Projekty doplňku VSTO, můžete přidat <xref:Microsoft.Office.Tools.Word.Bookmark> ovládací prvky pro všechny otevřené dokumenty za běhu. Další informace najdete v tématu [postupy: Přidání záložku ovládací prvky do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md).

## <a name="bind-data-to-the-control"></a>Vázání dat k ovládacímu prvku
 A <xref:Microsoft.Office.Tools.Word.Bookmark> řízení podporuje jednoduché datové vazby. Záložka by měla být vázána na zdroje dat pomocí <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> vlastnost. Je výchozí vlastnost vazby dat záložky <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> vlastnost.

 Při aktualizaci dat v datové sadě vázané <xref:Microsoft.Office.Tools.Word.Bookmark> řízení zobrazuje změny.

 V projektech na úrovni dokumentu, můžete také vázat data na záložky pomocí **zdroje dat** okno. Další informace najdete v tématu [postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md).

## <a name="formatting"></a>Formátování
 Formátování, které lze použít pro <xref:Microsoft.Office.Interop.Word.Bookmark> lze použít pro <xref:Microsoft.Office.Tools.Word.Bookmark> ovládacího prvku. Toto formátování zahrnuje písma, odsazení, mezery, číslování a styly.

## <a name="assign-text-to-the-bookmark"></a>Záložce přiřadit textu
 Další rozdíl mezi <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> objektu a <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> ovládací prvek je, jak se chová při přiřazení text na záložku. Pokud přiřadíte textu nulovou délkou <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType>, se připojí text doprava záložky a Záložka zůstane nulové délky. Ale pokud přiřadíte textu nulovou délkou <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>, text je vložen do záložky a délka záložku zasahuje do celkový počet znaků, vložit.

 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> Řízení má také <xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType> vlastnost. Tato vlastnost se liší od <xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType> vlastnost, která je k dispozici na <xref:Microsoft.Office.Tools.Word.Bookmark.Range?displayProperty=nameWithType> vlastnost <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> ovládací prvek, nebo <xref:Microsoft.Office.Interop.Word.Bookmark.Range?displayProperty=nameWithType> vlastnost <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> objektu.

|Text – vlastnost|Popis|
|-------------------|-----------------|
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType>|Pomocí této vlastnosti můžete zobrazit text v záložce a nechte záložku v dokumentu. Přiřazení text na záložku rozšíří rozsah záložku a nedojde k odstranění záložky.<br /><br /> Například `Bookmark1.Text = "Hello world"` vloží text do záložky a neporušené záložky.|
|<xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType>|Pomocí této vlastnosti můžete zobrazit text v umístění záložku a automaticky odstraní záložky. Například `Bookmark1.Range.Text = "Hello world"` vloží text do záložky a odstraní záložky.|

## <a name="rename-the-control-at-design-time"></a>Přejmenování ovládacího prvku v době návrhu
 V projektech na úrovni dokumentu, při přetažení <xref:Microsoft.Office.Tools.Word.Bookmark> řídit z **sada nástrojů** do dokumentu sady Visual Studio automaticky vygeneruje název ovládacího prvku. Můžete změnit název ovládacího prvku **vlastnosti** okno.

## <a name="overlapping-controls"></a>Překrývající se ovládací prvky
 Ovládacích prvků záložek můžete překrývají. Aby se stejný text může být sdílen více než jeden záložky. Přiřadíte-li nový text do jednoho z překrývající se záložky, obsahuje pouze nového textu a záložky už překrývat. Další záložku nyní obsahuje pouze text, který nebyl sdílen mezi původní překrývající se záložky.

 Následující tabulka ukazuje, jak se věta "Toto je ukázkový text". je sdílen dvě překrývající se záložky:

|Záložka|Text|
|--------------|----------|
|Překrývající se záložky|[Toto je ukázkový {] text.}|
|Bookmark1|Zde je ukázka|
|Bookmark2|Ukázkový text.|

 Chcete-li přiřadit nový text "To náhrada není dostupná." Bookmark1 záložky nepřekrývaly a Bookmark2 zachová pouze text, který není součástí Bookmark1 původně.

|Záložka|Text|
|--------------|----------|
|Dva samostatné záložky|[Toto je nahrazení] {text}.|
|Bookmark1|Toto je nahrazení|
|Bookmark2|text.|

Pokud změníte text záložka, která obsahuje jiné záložku, vnitřní záložka se neodstraní. Vnitřní záložku však se změní na prázdný záložku a přesune na konec vnější záložku.

Následující tabulka ukazuje, jak se věta "Toto je ukázkový text". je sdílen záložku, který je obsažený v jiné záložku:

|Záložka|Text|
|--------------|----------|
|Překrývající se záložky|[Toto je text {ukázka}].|
|Bookmark1|Toto je ukázkový text.|
|Bookmark2|ukázka|

 Chcete-li přiřadit nový text "To náhrada není dostupná." Pokud chcete Bookmark1 už překrývající se záložky a Bookmark2 se změní na prázdný záložku, který se nachází na konci Bookmark1.

|Záložka|Text|
|--------------|----------|
|Dva samostatné záložky|[Toto je nahrazení.]{}|
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

- [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)
- [Postupy: Přidání ovládacích prvků záložek do dokumentů aplikace Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [Návod: Vytváření místních nabídek pro záložky](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)