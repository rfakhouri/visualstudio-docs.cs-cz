---
title: 'Postupy: Přidání ovládacích prvků XMLMappedRange do listů'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: cef35cd1aa19ad27e7c47227b726a44756b0fae8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085713"
---
# <a name="how-to-add-xmlmappedrange-controls-to-worksheets"></a>Postupy: Přidání ovládacích prvků XMLMappedRange do listů
  Při mapování platný element XML do buňky v aplikaci Microsoft Office Excel sady Visual Studio automaticky přidá <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládacího prvku do listu.

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

> [!NOTE]
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Ovládací prvek není k dispozici na **nástrojů** nebo **zdroje dat** okna. Kromě toho nelze vytvořit <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> řídí prostřednictvím kódu programu.

## <a name="to-add-an-xmlmappedrange-control-to-a-worksheet"></a>Chcete-li přidat xmlmappedrange – ovládací prvek do listu

1. Otevřete Excelový sešit v návrháři aplikace Visual Studio.

2. Otevřete list, ve které chcete přidat ovládací prvek.

3. Na **Developer** klikněte na tlačítko **zdroj**.

    > [!NOTE]
    >  Pokud **Developer** karta není zobrazena na pásu karet, musíte ho nejdřív povolit. Další informace najdete v tématu [jak: Zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

     **XML použitého jako zdroj** se zobrazí v podokně úloh.

4. V **XML použitého jako zdroj** podokna úloh, klikněte na tlačítko **mapování XML**.

5. V **mapování XML** dialogové okno, klikněte na tlačítko **přidat**.

     **XML použitého jako zdroj** zobrazí se dialogové okno.

6. Výběr schématu XML z **XML použitého jako zdroj** dialogové okno a klikněte na tlačítko **otevřít**.

     Schéma se přidá do **mapování XML** dialogové okno.

7. V **mapování XML** dialogové okno, klikněte na tlačítko **OK**.

8. Přetáhněte element z **XML použitého jako zdroj** podokna úloh do buňky v listu.

     <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Je vytvořen a přidán do projektu.

    > [!NOTE]
    >  Pokud přetáhnete nadřazený element z **XML použitého jako zdroj** podokna úloh <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek vytvořen.

## <a name="see-also"></a>Viz také:
- [Xmlmappedrange – ovládací prvek](../vsto/xmlmappedrange-control.md)
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Postupy: Mapování schémat na listy v prostředí Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)
