---
title: 'Postupy: Přizpůsobení předdefinované karty'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- built-in tabs [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8e6f2d0da758a8897f28a22dec8adf1f8e05a36c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419449"
---
# <a name="how-to-customize-a-built-in-tab"></a>Postupy: Přizpůsobení předdefinované karty
  Můžete přidat skupiny a ovládací prvky k předdefinované kartě. Vestavěná karta je karta, který je již na pásu karet aplikace Microsoft Office. Například **Data** karta je integrovanou kartou v aplikaci Excel. Když vytvoříte vlastní skupiny, se zobrazí poslední na kartě, ale vaši skupinu můžete přesunout kamkoli na kartě.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

> [!NOTE]
> Můžete přidat skupiny k předdefinované kartě, ale předdefinované skupiny nelze odebrat z předdefinované karty.

### <a name="to-add-groups-to-a-built-in-tab"></a>Přidání skupin do předdefinované karty

1. Klikněte pravým tlačítkem na soubor kódu pásu karet v **Průzkumníka řešení**a potom klikněte na tlačítko **Návrhář zobrazení**.

    > [!NOTE]
    > Pokud soubor kódu pásu karet se nezobrazí v **Průzkumníka řešení**, je nutné přidat **položky pásu karet** do projektu. Zobrazit [jak: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md).

2. Klikněte pravým tlačítkem na libovolné kartě v Návrháři pásu karet a potom klikněte na tlačítko **vlastnosti**.

3. V **vlastnosti** okna, rozbalte **ControlId** vlastnost a poté nastavte **ControlIdType** vlastnost **Office**.

4. Nastavte **OfficeId** vlastnost *ID ovládacího prvku* předdefinované karty, kterou chcete upravit.

     ID ovládacího prvku je název, který jednoznačně identifikuje karty, skupiny a ovládací prvky, které jsou integrované do aplikace Microsoft Office.

     Seznam ID ovládacích prvků naleznete v tématu [soubory nápovědy Office 2010: Office fluent uživatelského rozhraní ovládacího prvku identifikátory](http://go.microsoft.com/fwlink/?LinkID=181052).

5. Z **ovládací prvky Ribbon Office** karty **nástrojů**, přetáhněte skupin na kartě.

    > [!NOTE]
    > Předdefinované skupiny v Návrháři nezobrazí. Proto je jediný způsob, jak určit, jestli pracujete s předdefinovanou kartu prozkoumat **ControlId** vlastnosti na kartě.

### <a name="to-position-groups-on-a-built-in-tab"></a>Pokud chcete umístit na integrované kartě skupiny

1. V Návrháři pásu karet vyberte vlastní skupiny.

2. V **vlastnosti** okna, rozbalte **pozice** vlastnost.

3. Nastavte **PositionType** k odpovídající hodnotě:

    - **BeforeOfficeId** umístí skupině před zadaným předdefinovanou skupinu.

    - **AfterOfficeId** umístí skupině po zadané integrované skupiny.

4. Nastavte **OfficeId** vlastnosti ID ovládacího prvku předdefinovanou skupinu.

     Seznam ID ovládacích prvků naleznete v tématu [soubory nápovědy Office 2010: Office fluent uživatelského rozhraní ovládacího prvku identifikátory](http://go.microsoft.com/fwlink/?LinkID=181052).

## <a name="see-also"></a>Viz také:
- [Přehled pásu karet](../vsto/ribbon-overview.md)
- [Návrhář pásu karet](../vsto/ribbon-designer.md)
- [Pás karet – XML](../vsto/ribbon-xml.md)
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
- [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [Postupy: Změna umístění karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)
- [Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [Postupy: Zobrazení doplňku uživatele chyb rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)
