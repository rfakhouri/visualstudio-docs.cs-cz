---
title: Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data, displaying
- data sources, displaying data
- Data Sources window
- dislaying data
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d27975cf387c92e5afcc61bd267f383a6bed414a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747388"
---
# <a name="bind-controls-to-data-in-visual-studio"></a>Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio
Data můžete zobrazit uživatelům vaší aplikace pomocí vytvoření vazby dat s ovládacími prvky. Tyto ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okno na návrhovou plochu nebo ovládacích prvků na prostor v sadě Visual Studio.

 Toto téma popisuje zdroje dat, které můžete použít k vytvoření ovládací prvky vázané na data. Popisuje také některé obecné úkoly při datové vazby. Podrobnější informace o tom, jak vytvořit ovládací prvky vázané na data najdete v tématu [vazby Windows Forms – ovládací prvky k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) a [prvky vazby WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

## <a name="data-sources"></a>Zdroje dat
 V kontextu vazby dat se zdroji dat představuje data v paměti, které mohou být vázány na uživatelské rozhraní. V praxi může být zdroje dat třídu Entity Framework, datové sady, koncový bod služby, který je zapouzdřený v objekt proxy .NET, LINQ to SQL třídy, nebo všechny .NET objektu nebo kolekci. Některé zdroje dat umožňují vytvořit ovládací prvky vázané na data tak, že přetáhnete položky z **zdroje dat** okno, zatímco jiné zdroje dat nepodporují. Následující tabulka uvádí, jaké zdroje dat nejsou podporovány.

|Zdroj dat|Podpora přetažení myší v **Návrhář formulářů Windows**|Podpora přetažení myší v **Návrháře WPF**|Podpora přetažení myší v **návrháře Silverlight**|
|-----------------|---------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|
|Datová sada|Ano|Ano|Ne|
|Entity Data Model|Ano<sup>1</sup>|Ano|Ano|
|Třídy LINQ to SQL|Ne<sup>2</sup>|Ne<sup>2</sup>|Ne<sup>2</sup>|
|Služby (včetně [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], WCF služeb a webových služeb)|Ano|Ano|Ano|
|Objekt|Ano|Ano|Ano|
|SharePoint|Ano|Ano|Ano|

 1. Generování modelu pomocí **datového modelu Entity** průvodce, přetáhněte těchto objektů do návrháře.

 2. Třídy LINQ to SQL nejsou uvedeny v **zdroje dat** okno. Můžete však přidat nový zdroj dat objekt založený na LINQ na třídy SQL a poté přetáhněte těchto objektů do návrháře vytvořit ovládací prvky vázané na data. Další informace najdete v tématu [návod: vytváření třídy LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).

## <a name="data-sources-window"></a>okno Zdroje dat
 Zdroje dat jsou k dispozici pro váš projekt jako položky v **zdroje dat** okno. Toto okno se zobrazí, nebo je přístupný z **zobrazení** nabídky, když návrhová plocha formuláře je aktivní okno ve vašem projektu. Přetahování položek z tohoto okna vytvořit ovládací prvky vázané na základní data a můžete také konfigurovat zdroje dat kliknutím pravým tlačítkem myši.

 ![okno Zdroje dat](../data-tools/media/raddata-data-sources-window.png)

 Pro každý typ dat, který se zobrazí v **zdroje dat** okně ovládacího prvku výchozí se vytvoří při přetáhněte ji do návrháře. Před přetáhnete položky z **zdroje dat** okno, můžete změnit ovládací prvek, který bude vytvořen. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

## <a name="tasks-involved-in-binding-controls-to-data"></a>Úkoly při vytvoření vazby ovládacích prvků k datům
 Následující tabulka uvádí některé z nejčastějších úloh, můžete provést k vytvoření vazby ovládacích prvků k datům.

|Úloha|Další informace|
|----------|----------------------|
|Otevřete **zdroje dat** okno.|Otevřete v editoru návrhová plocha a zvolte **zobrazení** > **zdroje dat**.|
|Přidání zdroje dat do projektu.|[Přidat nové zdroje dat](../data-tools/add-new-data-sources.md)|
|Nastavení ovládacího prvku, který je vytvořen při přetažení položku z **zdroje dat** okna návrháře.|[Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdrojů dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|
|Úprava ovládacích prvků, které jsou přidružené položky v seznamu **zdroje dat** okno.|[Přidání vlastních ovládacích prvků do okna zdrojů dat](../data-tools/add-custom-controls-to-the-data-sources-window.md)|
|Vytvořte ovládací prvky vázané na data.|[Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [Vytvoření vazby ovládacích prvků WPF k datům v sadě Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)|
|Vytvořit vazbu k objektu nebo kolekci.|[Vazby objektů v sadě Visual Studio](../data-tools/bind-objects-in-visual-studio.md)|
|Filtrování dat, který se zobrazí v uživatelském rozhraní.|[Filtrování a řazení dat ve formulářové aplikaci Windows](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|
|Přizpůsobte titulky pro ovládací prvky.|[Úprava způsobu, kterým Visual Studio vytváří titulky pro ovládací prvky vázané daty](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|

## <a name="see-also"></a>Viz také

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Windows Forms – datová vazba](/dotnet/framework/winforms/windows-forms-data-binding)