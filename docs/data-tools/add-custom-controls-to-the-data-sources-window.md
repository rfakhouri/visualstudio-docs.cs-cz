---
title: Přidání vlastních ovládacích prvků do okna zdroje dat
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.datasource.howtoaddcustomcontrol
helpviewer_keywords:
- Data Sources Window, adding controls
- controls [Visual Studio], adding to Data Sources Window
- DefaultBindingPropertyAttribute class, using
- LookupBindingPropertiesAttribute class, using
- ComplexBindingPropertiesAttribute class, using
- Data Sources Window, selecting controls
ms.assetid: 8c43e7d2-ba94-4d9b-96de-3aa971955afd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5db34de3244f7ee38ba4ef33c71b251f2bdbb6b0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="add-custom-controls-to-the-data-sources-window"></a>Přidání vlastních ovládacích prvků do okna zdroje dat
Když přetáhnete položky z **zdroje dat** okna návrhové ploše k vytvoření ovládacího prvku vázané na data, můžete vybrat typ ovládacího prvku, který vytvoříte. Každá položka v okně má rozevíracího seznamu, který zobrazuje ovládacích prvků, které můžete vybrat z. Sadu ovládacích prvků, které jsou spojené s každou položku je určen podle datový typ položky. Pokud ovládací prvek, který chcete vytvořit v seznamu nezobrazí, můžete podle pokynů v tomto tématu Přidání ovládacího prvku do seznamu.

 Další informace o výběru ovládací prvky vázané na data vytvoření pro položky v **zdroje dat** okně najdete v části [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, na **nástroje** nabídce vyberte možnost **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

##  <a name="customizinglist"></a> Přizpůsobení seznamu vazbu ovládacích prvků pro datový typ
 Přidat nebo odebrat ze seznamu dostupných ovládacích prvků pro položky v ovládacích prvcích **zdroje dat** okno, které mají určitý datový typ, proveďte následující kroky.

#### <a name="to-select-the-controls-to-be-listed-for-a-data-type"></a>Vyberte ovládací prvky uvedené pro datový typ

1.  Ujistěte se, že Návrháře WPF nebo Návrhář formulářů Windows je otevřené.

2.  V **zdroje dat** okně klikněte na položku, která je součástí, které jste přidali do okna zdroje dat a klikněte na rozevírací nabídku pro položku.

3.  V rozevírací nabídce klikněte na **přizpůsobit**. Jeden z následujících dialogových otevře:

    -   Pokud je otevřený, Návrhář formulářů Windows **přizpůsobení uživatelského rozhraní dat** stránky **možnosti** otevře se dialogové okno.

    -   Pokud je otevřený, Návrhář WPF **přizpůsobit vazbu ovládacího prvku** otevře se dialogové okno.

4.  V dialogovém okně vyberte datový typ z **datový typ** rozevíracího seznamu.

    -   Chcete-li upravit seznam ovládacích prvků pro tabulku či objekt, vyberte **[seznam]**.

    -   Chcete-li přizpůsobit seznam ovládacích prvků pro sloupec tabulky nebo vlastnost objektu, vyberte datový typ sloupce nebo vlastnost v příslušné úložiště dat.

    -   Chcete-li upravit seznam ovládacích prvků pro zobrazení datových objektů, které mají vlastní tvary, vyberte **[jiné]**. Vyberte například **[jiné]** Pokud vaše aplikace má vlastní ovládací prvek, který zobrazuje data z více než jednu vlastnost určitého objektu.

5.  V **související ovládací prvky** zaškrtněte, každý ovládací prvek, který chcete, aby byly dostupné pro vybraný typ dat nebo zrušte výběr všech ovládacích prvků, které chcete odebrat ze seznamu.

    > [!NOTE]
    >  Pokud ovládací prvek, který chcete vybrat nezobrazí v **související ovládací prvky** pole, je nutné přidat do seznamu ovládacího prvku. Další informace najdete v tématu [přidání ovládacích prvků do seznamu z související ovládací prvky pro datový typ](#addingcontrols).

6.  Click **OK**.

7.  V **zdroje dat** okna, klikněte na položku dat zadejte přidružené právě jeden nebo více ovládacích prvků a klikněte na rozevírací nabídku pro položku.

     Ovládací prvky, které jste vybrali v **související ovládací prvky** pole se nyní zobrazí v rozevírací nabídce pro položku.

##  <a name="addingcontrols"></a> Přidání ovládacích prvků do seznamu přidružených ovládacích prvcích pro datový typ
 Pokud chcete přiřadit ovládací prvek s datovým typem, ale ovládací prvek v nezobrazí **související ovládací prvky** pole ovládacího prvku musíte přidat do seznamu. Ovládací prvek musí být umístěn v aktuálním řešení nebo v odkazované sestavení. Také musí být k dispozici v **sada nástrojů**, a atribut, který určuje chování vazby dat ovládacího prvku.

#### <a name="to-add-controls-to-the-list-of-associated-controls"></a>K přidávání ovládacích prvků do seznamu přidružených ovládacích prvcích

1.  Přidejte požadované řízení na **sada nástrojů** kliknutím pravým tlačítkem myši **sada nástrojů** a výběrem **zvolit položky**.

     Ovládací prvek musí mít jednu z následujících atributů.

    |Atribut|Popis|
    |---------------|-----------------|
    |<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Implementace tohoto atributu na jednoduché ovládací prvky, které zobrazují jeden sloupec (nebo vlastnost) data, například <xref:System.Windows.Forms.TextBox>.|
    |<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Implementace tohoto atributu na ovládací prvky, které zobrazují seznamy (nebo tabulky) dat, například <xref:System.Windows.Forms.DataGridView>.|
    |<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Implementace tohoto atributu na ovládací prvky, které zobrazují seznamy (nebo tabulky), data, ale taky potřeba k dispozici jeden sloupec nebo vlastnost, například <xref:System.Windows.Forms.ComboBox>.|

2.  Pro Windows Forms na **možnosti** dialogové okno, otevřete **přizpůsobení uživatelského rozhraní dat** stránky. Nebo WPF, otevřete **přizpůsobit vazbu ovládacího prvku** dialogové okno. Další informace najdete v tématu [přizpůsobení seznamu vazbu prvky pro datový typ](#customizinglist).

3.  V **související ovládací prvky** pole ovládací prvek, který jste právě přidali **sada nástrojů** by se měla zobrazit.

    > [!NOTE]
    >  Seznam přidružených ovládacích prvcích lze přidat pouze ovládací prvky, které jsou umístěné v aktuálním řešení a v odkazované sestavení. (Ovládací prvky musí také implementovat jeden z atributů datové vazby v předchozí tabulce.) K vytvoření vazby dat vlastní ovládací prvek, který není k dispozici v **zdroje dat** okna, přetáhněte ovládací prvek z **sada nástrojů** do návrhová plocha a pak přetáhněte položka pro vazby z **dat Zdroje** okna do ovládacího prvku.

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)