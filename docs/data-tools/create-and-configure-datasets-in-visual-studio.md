---
title: Vytvoření a konfigurace datové sady v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- typed datasets, creating
- datasets, creating
- datasets, configuring
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d7aac502f32941d825fda77c43ae07e82c4e9db3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="create-and-configure-datasets-in-visual-studio"></a>Vytvoření a konfigurace datové sady v sadě Visual Studio

A *datovou sadu* sadu objektů, které ukládají data z databáze v paměti a podporu, chcete-li povolit sledování změn je vytvářet, číst, aktualizovat a odstraňovat operace na data bez nutnosti byly neustále připojené k databázi. Datové sady byly navrženy pro jednoduché *forms nad daty* obchodních aplikací. Pro nové aplikace zvažte použití rozhraní Entity Framework pro ukládání a modelu data v paměti. Pro práci s datovými sadami, byste měli mít základní znalosti koncepce databáze.

Vytvoříte představuje zadaný <xref:System.Data.DataSet> třídy v sadě Visual Studio v době návrhu pomocí **Průvodce konfigurací zdroje dat**. Informace o vytváření datových sad prostřednictvím kódu programu najdete v tématu [vytváření datovou sadu (ADO.NET)](/dotnet/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset).

## <a name="create-a-new-dataset-by-using-the-data-source-configuration-wizard"></a>Vytvořit novou sadu dat pomocí Průvodce konfigurací zdroje dat

1.  Na **projektu** nabídky, klikněte na tlačítko **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

2.  Vyberte typ zdroje dat, která se připojují k.

     ![Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png "Průvodce konfigurací zdroje dat")

3.  Pro databáze vyberte databázi nebo databáze, které bude zdroj dat pro datovou sadu.

     ![Zdroj dat, vyberte připojení](../data-tools/media/data-source-choose-a-connection.png "zdroje dat vyberte připojení")

4.  Vyberte tabulky (nebo jednotlivé sloupce), uložené procedury, funkce a zobrazení z databáze, kterou chcete být reprezentován v datové sadě.

     ![Vyberte objekty databáze](../data-tools/media/raddata-chose-objects.png "raddata pokusit objekty")

5.  Klikněte na tlačítko **Dokončit**.

6.  Datová sada se zobrazí jako uzel v **Průzkumníku řešení**:

     ![Datovou sadu v Průzkumníku řešení](../data-tools/media/dataset-in-solution-explorer.png "datovou sadu v Průzkumníku řešení")

     Klikněte na tento uzel a datové sady se zobrazí v **návrháře DataSet**. Všimněte si, že má každá tabulka v datové sadě přidružené TableAdapter objekt, který je reprezentován v dolní části. Adaptér tabulky se používá k naplnění datové sady a volitelně odesílat příkazy do databáze.

     ![Návrháři DataSet](../data-tools/media/dataset-designer.png "návrháře DataSet")

7.  Vztah řádky, které připojení tabulky představují relace mezi tabulkami, jak jsou definovány v databázi. Omezení cizího klíče v databázi ve výchozím nastavení, jsou reprezentovány jako vztah pouze k aktualizaci a odstranění pravidla nastavená na hodnotu none. Obvykle se jedná, co chcete použít. Ale můžete kliknout na řádky, které se otevře **vztah** dialogové okno, kde můžete změnit chování hierarchických aktualizací. Další informace najdete v tématu [vztahy v datových sadách](../data-tools/relationships-in-datasets.md) a [hierarchické aktualizace](../data-tools/hierarchical-update.md).

     ![Dialogové okno datové sady vztah](../data-tools/media/raddata-relation-dialog.png "raddata relace dialogu")

8.  Klikněte na tlačítko Tabulka, tabulka adaptér nebo název sloupce v tabulce zobrazíte její vlastnosti v **vlastnosti** okno. Můžete upravit některé hodnoty v tomto poli. Jenom nezapomeňte, že budete upravovat datovou sadu, není zdrojové databáze.

     ![Vlastnosti datové sady sloupců](../data-tools/media/dataset-column-properties.png "sloupce vlastnosti datové sady")

9. Můžete přidat nové tabulky nebo adaptéry tabulek do datové sady, nebo přidejte nové dotazy pro existující adaptéry tabulek nebo zadejte nové vztahy mezi tabulkami přetažením těchto položek z **sada nástrojů** kartě. Na této kartě se zobrazí, když **návrháře DataSet** je aktivní.

     ![Datová sada nástrojů](../data-tools/media/raddata-dataset-toolbox.png "raddata datové sady nástrojů")

10. V dalším kroku chcete pravděpodobně určete, jak k naplnění datové sady daty. Pro, který můžete použít **Průvodce nastavením TableAdapter**. Další informace najdete v tématu [vyplnění datové sady s použitím TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).

## <a name="add-a-database-table-or-other-object-to-an-existing-dataset"></a>Přidat tabulku databáze nebo jiného objektu do existující datovou sadu

Tento postup ukazuje, jak přidat tabulku ze stejné databáze, který jste použili nejdřív vytvořit datová sada.

1.  Klikněte na uzel datové sady v **Průzkumníku řešení** tím návrháře dataset do fokus.

2.  Klikněte **zdroje dat** kartě na levém okraji sady Visual Studio, nebo zadejte `Data Sources` v **Snadné spuštění**.

3.  Klikněte pravým tlačítkem na uzel datové sady a vyberte **konfigurace zdroje dat pomocí průvodce**.

     ![Kontextová nabídka zdroje dat](../data-tools/media/data-source-context-menu.png "zdroj dat kontextové nabídky")

4.  Použijte průvodce k určení, které další tabulky nebo uložené procedury nebo jiného databázového objektu, chcete-li přidat do datové sady.

## <a name="add-a-stand-alone-data-table-to-a-dataset"></a>Umožňuje přidat tabulku samostatné data do datové sady

1.  Otevřete datovou sadu v **návrháře Dataset**.

2.  Přetáhněte <xref:System.Data.DataTable> třídy z **datovou sadu** kartě **sada nástrojů** na **návrháře Dataset**.

3.  Přidáte sloupce, které chcete definovat datová tabulka. Klikněte pravým tlačítkem na tabulky a zvolte **Přidat > sloupec**. Použití **vlastnosti** okna v případě potřeby nastavte datový typ sloupce a klíč.

4.  Samostatné tabulky muset implementace `Fill` logiku v samostatných tabulkách tak, že je můžete vložit s daty. Informace o vyplnění tabulky samostatné dat, v tématu [naplňování datové sady z modul DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).

## <a name="see-also"></a>Viz také

- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)