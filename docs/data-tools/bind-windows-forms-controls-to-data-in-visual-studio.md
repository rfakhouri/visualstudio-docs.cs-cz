---
title: Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- data [Windows Forms], data sources
- Windows Forms, data binding
- Windows Forms, displaying data
- displaying data on forms
- forms, displaying data
- data sources, displaying data
- displaying data, Windows Forms
- data [Windows Forms], displaying
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4652d8dd3e9be582bc15c4644711accc06fd283f
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845519"
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio
Data můžete zobrazit uživatelům vaší aplikace pomocí vytvoření vazby dat do formulářů Windows. Chcete-li vytvořit tyto ovládací prvky vázané na data, přetáhněte položky z **zdroje dat** okna do Windows Forms designerem v sadě Visual Studio.

![Operace přetažení zdroje dat](../data-tools/media/raddata-data-source-drag-operation.png)

Před přetahování položek, můžete nastavit typ ovládacího prvku, který chcete vytvořit vazbu na. V závislosti na tom, zda zvolíte tabulky sám sebe nebo u jednotlivých sloupců se zobrazují různé hodnoty.  Můžete také nastavit vlastní hodnoty. Pro tabulku **podrobnosti** znamená, že každý sloupec je vázána na samostatné ovládacího prvku.

![Svázat zdroj dat se DataGridView](../data-tools/media/raddata-bind-data-source-to-datagridview.png)

## <a name="bindingsource-and-bindingnavigator-controls"></a>BindingSource a BindingNavigator – ovládací prvky
<xref:System.Windows.Forms.BindingSource> Součást má dva účely. Nejprve poskytuje úroveň abstrakce, při vytváření vazby ovládacích prvků k datům. Ovládací prvky na formuláři je vázána na <xref:System.Windows.Forms.BindingSource> součásti místo přímo ke zdroji dat. Druhý umožňuje spravovat kolekce objektů. Přidání typu k <xref:System.Windows.Forms.BindingSource> vytvoří seznam daného typu.

Další informace o <xref:System.Windows.Forms.BindingSource> součást, najdete v části:

-   [BindingSource – komponenta](/dotnet/framework/winforms/controls/bindingsource-component)

-   [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview)

-   [Architektura součásti BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-architecture)

[BindingNavigator – ovládací prvek](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms) poskytuje uživatelské rozhraní pro procházení dat, které zobrazuje aplikace systému Windows.

## <a name="bind-to-data-in-a-datagridview-control"></a>Vázání dat v ovládacím prvku DataGridView
Pro [DataGridView – ovládací prvek](/dotnet/framework/winforms/controls/datagridview-control-overview-windows-forms), celá tabulka je vázána na daný jeden ovládací prvek. Při přetažení **DataGridView** do formuláře, odstranit nástroj pro procházení záznamů (<xref:System.Windows.Forms.BindingNavigator>) se zobrazí také. A [datovou sadu](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent. Na následujícím obrázku [TableAdapterManager](https://msdn.microsoft.com/library/bb384426.aspx) je také přidán, protože tabulka Zákazníci má vztah k tabulce objednávky. Tyto proměnné jsou všechny deklarované v automaticky vygenerovaný kód jako soukromé členy v třídě formuláře. Automaticky generovaný kód pro naplnění **DataGridView** se nachází v `Form_Load` obslužné rutiny události. Kód pro ukládání dat k aktualizaci databáze se nachází v `Save` obslužné rutiny události pro **BindingNavigator**. Můžete přesunout nebo upravit tento kód, podle potřeby.

![Rutina GridView s BindingNavigator](../data-tools/media/raddata-gridview-with-bindingnavigator.png)

Můžete přizpůsobit chování **DataGridView** a **BindingNavigator** kliknutím na inteligentní značky v pravém horním rohu každé:

![DataGridView – a vytvoření vazby Navigátor inteligentní značky](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png)

Pokud ovládací prvky aplikace vyžaduje nejsou dostupné v rámci **zdroje dat** okno, můžete přidat ovládací prvky. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

Můžete také přetáhnout položky z **zdroje dat** oken na ovládací prvky již ve formuláři pro vytvoření vazby ovládacího prvku k datům. Ovládací prvek, který je již vázána na data má jeho data, která vazby obnovit položky naposledy přetáhli ho. Být cílů platné umístění, musí být schopná zobrazit základní datový typ položky taženou do z ovládacích prvků **zdroje dat** okno. Například není platný přetáhněte položku, která má datový typ <xref:System.DateTime> na <xref:System.Windows.Forms.CheckBox>, protože <xref:System.Windows.Forms.CheckBox> není schopná zobrazit datum.

## <a name="bind-to-data-in-individual-controls"></a>Vázání dat v jednotlivých ovládacích prvků
Po vytvoření vazby zdroje dat **podrobnosti**, každý sloupec v datové sadě je vázán na samostatný prvek.

![Podrobnosti o svázat zdroj dat](../data-tools/media/raddata-bind-data-source-to-details.png)

> [!IMPORTANT]
> Všimněte si, že na předchozím obrázku, přetáhněte z vlastnosti objednávek zákazníků tabulky, není v této tabulce. Pomocí vazby ke `Customer.Orders` vlastností, navigační příkazy provedené v **DataGridView** se okamžitě projeví v ovládacích prvcích podrobnosti. Pokud jste přetáhli v tabulce, ovládací prvky by být stále vázaná k datové sadě, ale nemohli je synchronizovány s **DataGridView**.

Následující obrázek znázorňuje výchozí ovládací prvky vázané na data, které jsou přidány do formuláře po vlastnost objednávky v tabulce Zákazníci je vázána na **podrobnosti** v **zdroje dat** okno.

![Tabulka objednávky vázána na podrobnosti](../data-tools/media/raddata-orders-table-bound-to-details.png)

Všimněte si také, zda má každý ovládací prvek inteligentních značek. Tato značka umožňuje úpravy, které platí pro pouze tento ovládací prvek.

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Datové vazby v systému Windows Forms (rozhraní .NET Framework)](/dotnet/framework/winforms/windows-forms-data-binding)