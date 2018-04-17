---
title: 'Postupy: Přidání ovládacích prvků XMLMappedRange do listů | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fa0e6d6249ea9b7da3fb0ab57640b61fb38e7fe5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-xmlmappedrange-controls-to-worksheets"></a>Postupy: Přidání ovládacích prvků XMLMappedRange do listů
  Pokud namapujete XML element do buňky v aplikaci Microsoft Office Excel, Visual Studio automaticky přidá <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládacího prvku do listu.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Ovládací prvek není k dispozici na **sada nástrojů** nebo **zdroje dat** okno. Kromě toho nelze vytvořit <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> řídí prostřednictvím kódu programu.  
  
### <a name="to-add-an-xmlmappedrange-control-to-a-worksheet"></a>Chcete-li přidat do listu xmlmappedrange – ovládací prvek  
  
1.  Otevřete sešit aplikace Excel v návrháři Visual Studio.  
  
2.  Otevřete list, ve které chcete přidat ovládací prvek.  
  
3.  Na **vývojáře** , klikněte na **zdroj**.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný na pásu karet, je nutné povolit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
     **Zdroj dat XML** se zobrazí v podokně úloh.  
  
4.  V **zdroj dat XML** podokna úloh, klikněte na tlačítko **mapování XML**.  
  
5.  V **mapování XML** dialogové okno, klikněte na tlačítko **přidat**.  
  
     **Zdroj dat XML** zobrazí se dialogové okno.  
  
6.  Vyberte schématu XML z **zdroj dat XML** dialogové okno a klikněte na tlačítko **otevřete**.  
  
     Schéma se přidá do **mapování XML** dialogové okno.  
  
7.  V **mapování XML** dialogové okno, klikněte na tlačítko **OK**.  
  
8.  Přetáhněte element z **zdroj dat XML** podokna úloh do buňky v listu.  
  
     <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> Je vytvořen a přidán do projektu.  
  
    > [!NOTE]  
    >  Pokud přetáhněte nadřazený element z **zdroj dat XML** podokna úloh <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek je vytvořen.  
  
## <a name="see-also"></a>Viz také  
 [Xmlmappedrange – ovládací prvek](../vsto/xmlmappedrange-control.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Postupy: Mapování schémat na listy v prostředí Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  