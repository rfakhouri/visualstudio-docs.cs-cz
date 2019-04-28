---
title: 'Postupy: Přidání ovládacích prvků do zobrazení Backstage '
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c4241464fe8a43af882fbdbad0f898838e8fd897
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62826778"
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>Postupy: Přidání ovládacích prvků do zobrazení Backstage
  Návrhář pásu karet můžete použít k přidávání ovládacích prvků do nabídky, které se otevře po kliknutí **souboru** kartu. Při spuštění aplikace, ovládací prvky, které přidáte **souboru** karta se skupina s názvem **Add-ins**.

 Ovládací prvky nelze umístit před nebo za vestavěné ovládací prvky pomocí Návrháře pásu karet v sadě Visual Studio. Předdefinovaný ovládací prvek je ovládací prvek, který se již nachází v zobrazení Backstage. Pokud chcete umístit ovládací prvky před nebo po vestavěných ovládacích prvcích, je nutné použít pás karet XML. Další informace o **pásu karet (XML)**, naleznete v tématu [kódu XML pásu karet](../vsto/ribbon-xml.md). Další informace o úpravách zobrazení Backstage naleznete v tématu [Úvod do zobrazení Office 2010 Backstage pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182189) a [přizpůsobení zobrazení Office 2010 Backstage pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182188).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-controls-to-backstage-view"></a>Přidání ovládacích prvků do zobrazení Backstage

1. V návrhovém zobrazení otevřete položku pásu karet.

     Informace o tom, jak přidat **pás karet (vizuální návrhář)** položky do projektu, přečtěte si téma [jak: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md).

2. V Návrháři pásu karet klikněte na tlačítko **souboru** kartu.

     Otevře se Návrhář nabídek. Tuto návrhovou plochu neobsahuje žádné ovládací prvky.

3. Z **ovládací prvky Ribbon Office** karty **nástrojů**, přetáhněte kterýkoli z následujících ovládacích prvků na nabídce Návrhář:

    - Tlačítko

    - CheckBox

    - Galerie

    - Nabídka

    - Oddělovač

    - SplitButton

    - ToggleButton

4. Přetáhněte ovládací prvky a přesunout jej do nového umístění v nabídce.

## <a name="see-also"></a>Viz také:
- [Přehled pásu karet](../vsto/ribbon-overview.md)
- [Návrhář pásu karet](../vsto/ribbon-designer.md)
- [Pás karet – XML](../vsto/ribbon-xml.md)
- [Postupy: Začínáme přizpůsobení pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
