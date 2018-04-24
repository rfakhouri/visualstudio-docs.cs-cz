---
title: Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio – část 1 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c753c3818ac97fc353a90d4c7ae58f5f84f89b4b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio
Data můžete zobrazit uživatelům vaší aplikace pomocí vytvoření vazby dat [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] ovládací prvky. Chcete-li vytvořit tyto ovládací prvky vázané na data, můžete přetáhnout položky z **zdroje dat** okna do [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)] v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Toto téma popisuje některé z nejčastějších úloh, nástroje a třídy, které můžete použít k vytvoření vázané na data [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] aplikace.

 Obecné informace o tom, jak vytvořit ovládací prvky vázané na data v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], najdete v části [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Další informace o [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] datové vazby, najdete v části [přehled vazby dat](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>Úkoly při vytvoření vazby ovládacích prvků WPF k datům
 V následující tabulce jsou uvedeny úlohy, které lze provést tak, že přetáhnete položky z **zdroje dat** okna [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)].

|Úloha|Další informace|
|----------|----------------------|
|Vytvořte nové ovládací prvky vázané na data.<br /><br /> Navažte existující ovládací prvky na data.|[Vytvoření vazby ovládacích prvků WPF k datové sadě](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|Vytvořte ovládací prvky zobrazující související data ve vztahu nadřazený-podřízený, když uživatel vybere nadřazený záznam dat v jednom ovládacím prvku, jiný ovládací prvek pro tento vybraný záznam zobrazí související podřízená data.|[Zobrazení souvisejících dat v aplikaci WPF](../data-tools/display-related-data-in-wpf-applications.md)|
|Vytvoření *vyhledávací tabulky* který zobrazí informace z jedné tabulky na základě hodnoty pole cizího klíče v druhé tabulce.|[Vytváření vyhledávacích tabulek v aplikacích WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|Navažte ovládací prvek na obrázek v databázi.|[Vytvoření vazby ovládacích prvků k obrázkům z databáze](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>Cílů platné umístění
 Můžete přetáhnout položky **zdroje dat** okna pouze cílů platné umístění v [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)]. Existují dva hlavní druhy platných cílů přetažení: kontejnery a ovládací prvky. Kontejner je prvek uživatelského rozhraní, který obvykle obsahuje ovládací prvky. Kontejnerem je například mřížka nebo okno.

## <a name="generated-xaml-and-code"></a>Generovaný kód a XAML
 Když přetáhnete položky z **zdroje dat** okna [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)], [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] který definuje nový ovládací prvek vázané na data (nebo váže existujícího ovládacího prvku do zdroje dat). Pro některé zdroje dat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] také generuje kód v souboru kódu, který vyplní celé zdroj dat s daty.

 Následující tabulka uvádí [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] a kódu, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vygeneruje pro každý typ zdroje dat ve **zdroje dat** okno.

|Zdroj dat|Generování souboru XAML, který váže ovládací prvek na zdroj dat|Generování kódu, který vyplní daty zdroj dat|
|-----------------|-----------------------------------------------------------|--------------------------------------------------------|
|Datová sada|Ano|Ano|
|[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]|Ano|Ano|
|Služba|Ano|Ne|
|Objekt|Ano|Ne|

### <a name="datasets"></a>Datové sady
 Při přetažení tabulky nebo sloupce z **zdroje dat** okna návrháře, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , provede následující akce:

-   Přidá datovou sadu a nové <xref:System.Windows.Data.CollectionViewSource> k prostředkům kontejneru jste přetáhli položka, která má. <xref:System.Windows.Data.CollectionViewSource> Je objekt, který můžete použít k přejděte a zobrazení dat v datové sadě.

-   Vytvoří datové vazby pro ovládací prvek. Pokud přetáhnete položku na existující ovládací prvek v návrháři, XAML naváže ovládací prvek na položku. Pokud přetáhnete položky do kontejneru, XAML vytvoří ovládací prvek, který byl vybrán pro taženou položku a ovládacího prvku se váže k položce. Ovládací prvek je vytvořit uvnitř nový <xref:System.Windows.Controls.Grid>.

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] také provede tyto změny do souboru kódu na pozadí:

-   Vytvoří <xref:System.Windows.FrameworkElement.Loaded> obslužné rutiny události pro [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] elementu, který obsahuje ovládací prvek. Obslužné rutiny události do tabulky s daty, načte vyplní <xref:System.Windows.Data.CollectionViewSource> z kontejneru prostředků a pak díky první datové položky s aktuální položkou. Pokud <xref:System.Windows.FrameworkElement.Loaded> obslužné rutiny události již existuje, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přidá tento kód do stávající obslužné rutiny události.

### <a name="entity-data-models"></a>Modely dat entity
 Při přetažení pro entitu, nebo vlastnost entity z **zdroje dat** okna návrháře, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , provede následující akce:

-   Přidá nový <xref:System.Windows.Data.CollectionViewSource> k prostředkům kontejneru jste přetáhli položka, která má. <xref:System.Windows.Data.CollectionViewSource> Je objekt, který můžete použít k přejděte a zobrazení dat v entitě.

-   Vytvoří datové vazby pro ovládací prvek. Přetažením položky do existujícího ovládacího prvku v návrháři [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] vytvoří vazbu ovládacího prvku k položce. Pokud přetáhněte ji do kontejneru, [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] vytvoří ovládacího prvku která nebyla vybrána pro taženou položku a ovládacího prvku se váže k položce. Ovládací prvek je vytvořit uvnitř nový <xref:System.Windows.Controls.Grid>.

Sada Visual Studio rovněž provede následující změny v souboru s kódem na pozadí:

-   Přidá novou metodu, jež vrací dotaz pro entitu, kterou jste přetáhli do návrháře (nebo entitu obsahující vlastnost, kterou jste přetáhli do návrháře). Nová metoda má název Get*EntityName*dotaz, kde *EntityName* je název sady entit.

-   Vytvoří <xref:System.Windows.FrameworkElement.Loaded> obslužné rutiny události pro [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] elementu, který obsahuje ovládací prvek. Obslužné rutiny události volání Get*EntityName*metoda k vyplnění entity s daty, načte dotaz <xref:System.Windows.Data.CollectionViewSource> z kontejneru prostředků a pak díky první datové položky s aktuální položkou. Pokud <xref:System.Windows.FrameworkElement.Loaded> obslužné rutiny události již existuje, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přidá tento kód do stávající obslužné rutiny události.

### <a name="services"></a>Služby
 Při přetažení objekt služby nebo vlastnost z **zdroje dat** okna návrháře, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , vytvoří ovládacího prvku vázané na data (nebo vytvoří vazbu ovládacího prvku existující objekt nebo vlastnost). Ale [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nevygeneruje žádný kód, který vyplní celé objektu proxy služby s daty. Tento kód musíte napsat sami. Příklad, který ukazuje, jak to udělat, najdete v části [prvky vazby WPF služby WCF data Service](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

 Sada Visual Studio generuje jazyk XAML, který provede následující akce:

-   Přidá nový <xref:System.Windows.Data.CollectionViewSource> kontejneru, který jste přetáhli položka, která má na prostředky. <xref:System.Windows.Data.CollectionViewSource> Je objekt, který můžete použít k přejděte a zobrazení dat v objektu, která je vrácena službou.

-   Vytvoří datové vazby pro ovládací prvek. Přetažením položky do existujícího ovládacího prvku v návrháři [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] vytvoří vazbu ovládacího prvku k položce. Pokud přetáhněte ji do kontejneru, [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] vytvoří ovládacího prvku která nebyla vybrána pro taženou položku a ovládacího prvku se váže k položce. Ovládací prvek je vytvořit uvnitř nový <xref:System.Windows.Controls.Grid>.

### <a name="objects"></a>Objekty
 Při přetažení na objekt nebo vlastnost z **zdroje dat** okna návrháře, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , vytvoří ovládacího prvku vázané na data (nebo vytvoří vazbu ovládacího prvku existující objekt nebo vlastnost). Ale [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nevygeneruje žádný kód k vyplnění objekt s daty. Tento kód musíte napsat sami.

> [!NOTE]
>  Vlastní třídy musí být veřejné a ve výchozím nastavení, mít konstruktor bez parametrů. Jejich can'tbe vnořené tříd, které mají "tečku" v jejich syntaxi. Další informace najdete v tématu [XAML a vlastní třídy pro grafický subsystém WPF](/dotnet/framework/wpf/advanced/xaml-and-custom-classes-for-wpf).

 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generuje [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , provede následující akce:

-   Přidá nový <xref:System.Windows.Data.CollectionViewSource> kontejneru, který jste přetáhli položka, která má na prostředky. <xref:System.Windows.Data.CollectionViewSource> Je objekt, který můžete použít k přejděte a zobrazení dat v objektu.

-   Vytvoří datové vazby pro ovládací prvek. Pokud přetáhnete položku na existující ovládací prvek v návrháři, XAML naváže ovládací prvek na položku. Pokud přetáhnete položky do kontejneru, XAML vytvoří ovládací prvek, který byl vybrán pro taženou položku a ovládacího prvku se váže k položce. Ovládací prvek je vytvořit uvnitř nový <xref:System.Windows.Controls.Grid>.

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)