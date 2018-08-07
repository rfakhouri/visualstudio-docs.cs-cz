---
title: Vytvoření a konfigurace datových sad v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- typed datasets, creating
- datasets, creating
- datasets, configuring
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a65c1960e1648dce3bb8ff40d1dd6c50534934ff
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582229"
---
# <a name="create-and-configure-datasets-in-visual-studio"></a>Vytvoření a konfigurace datových sad v sadě Visual Studio

Datová sada je sada objektů, které ukládají data z databáze v paměti a podporují řešení change tracking umožňuje vytváření, čtení, aktualizace a odstranění (CRUD) operací na těchto datech, aniž byste museli být neustále připojeni k databázi. Datové sady byly navržené pro jednoduchou *formy nad daty* obchodních aplikací. Pro nové aplikace zvažte použití rozhraní Entity Framework ukládat a modelovat data v paměti. Pro práci s datovými sadami, byste měli mít základní znalost konceptů databáze.

Vytvoříte typovaného <xref:System.Data.DataSet> třídy v sadě Visual Studio v době návrhu pomocí **Průvodce konfigurací zdroje dat**. Informace o vytváření datových sad prostřednictvím kódu programu najdete v tématu [vytvoření datové sady (ADO.NET)](/dotnet/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset).

## <a name="create-a-new-dataset-by-using-the-data-source-configuration-wizard"></a>Vytvoření nové datové sady pomocí Průvodce konfigurací zdroje dat

1.  Na **projektu** nabídky, klikněte na tlačítko **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.

2.  Zvolte typ zdroje dat, ke kterému se připojuje.

     ![Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png)

3.  Zvolte databázi nebo databáze, které mají být zdroje dat pro datové sady.

     ![Zvolte připojení zdroje dat](../data-tools/media/data-source-choose-a-connection.png)

4.  Zvolte tabulky (nebo jednotlivé sloupce), uložených procedur, funkcí a zobrazení z databáze, kterou chcete být zastoupeny v datové sadě.

     ![Zvolit databázové objekty](../data-tools/media/raddata-chose-objects.png)

5.  Klikněte na tlačítko **Dokončit**.

6.  Datová sada se zobrazí jako uzel v **Průzkumníka řešení**.

     ![Datová sada v Průzkumníku řešení](../data-tools/media/dataset-in-solution-explorer.png)

     Klikněte na tento uzel a datová sada se zobrazí v **Návrhář DataSet**. Všimněte si, že má každá tabulka v datové sadě přidružené `TableAdapter` objektu, který je reprezentován v dolní části. Adaptér tabulka slouží k naplnění datové sady a volitelně odesílat příkazy do databáze.

     ![Návrhář DataSet](../data-tools/media/dataset-designer.png)

7.  Vztahu čáry, které spojují tabulky představují relací mezi tabulkami, jak jsou definovány v databázi. Ve výchozím omezení cizího klíče v databázi jsou reprezentovány jako vztah, aktualizace a odstranění pravidla nastavená na hodnotu none. Obvykle se jedná o co chcete. Ale můžete kliknout na řádky, zobrazí se **vztah** dialogové okno, kde můžete změnit chování hierarchických aktualizací. Další informace najdete v tématu [vztahy v datových sadách](../data-tools/relationships-in-datasets.md) a [hierarchické aktualizace](../data-tools/hierarchical-update.md).

     ![Dialogové okno relace datové sady](../data-tools/media/raddata-relation-dialog.png)

8.  Klepněte na tabulku, adaptér tabulky nebo název sloupce v tabulce zobrazíte její vlastnosti v **vlastnosti** okna. Některé hodnoty Tady můžete upravit. Jenom nezapomeňte, že budete upravovat datovou sadu, ne zdrojové databáze.

     ![Vlastnosti sloupce datové sady](../data-tools/media/dataset-column-properties.png)

9. Můžete přidat nové tabulky nebo adaptéry tabulek do datové sady, nebo přidejte nové dotazy pro existující adaptéry tabulek nebo zadejte nové vztahy mezi tabulkami přetažením položky z **nástrojů** kartu. Na této kartě se zobrazí, když **Návrhář DataSet** je aktivní.

     ![Datové sady nástrojů](../data-tools/media/raddata-dataset-toolbox.png)

10. V dalším kroku budete pravděpodobně chtít určete, jak k naplnění datové sady daty. K tomu použijete **Průvodce nastavením TableAdapter**. Další informace najdete v tématu [vyplnění datové sady s použitím objektů TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md).

## <a name="add-a-database-table-or-other-object-to-an-existing-dataset"></a>Přidat tabulku databáze nebo jiný objekt na existující sadu dat

Tento postup ukazuje, jak přidat tabulku ze stejné databáze, který jste použili k vytvoření datové sady.

1.  Klikněte na uzel datové sady v **Průzkumníka řešení** zapojit návrháři datových sad do fokus.

2.  Klikněte na tlačítko **zdroje dat** kartu na levém okraji sady Visual Studio, nebo zadejte parametr **zdroje dat** v **Snadné spuštění** pole.

3.  Klikněte pravým tlačítkem na uzel datové sady a vyberte **konfigurace zdroje dat pomocí průvodce**.

     ![Kontextová nabídka zdroje dat](../data-tools/media/data-source-context-menu.png)

4.  Chcete-li určit, jaké další tabulky, nebo uložené procedury nebo jiný objekt databáze, přidat do datové sady pomocí průvodce.

## <a name="add-a-stand-alone-data-table-to-a-dataset"></a>Přidání samostatné datové tabulky do datové sady

1.  Otevřete svou datovou sadu v **Návrhář Dataset**.

2.  Přetáhněte <xref:System.Data.DataTable> třídy z **datovou sadu** kartě **nástrojů** na **Návrhář Dataset**.

3.  Přidáte sloupce pro definování dat tabulky. Klikněte pravým tlačítkem na tabulku a zvolte **přidat** > **sloupec**. Použití **vlastnosti** okno, aby v případě potřeby nastavte datový typ sloupce a klíč.

4.  Nutné implementovat samostatné tabulky `Fill` logiku v samostatných tabulkách tak, aby vám je naplnit daty. Informace o vyplnění tabulky samostatné dat, naleznete v tématu [naplnění datové sady z adaptéru dat](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).

## <a name="see-also"></a>Viz také:

- [Nástroje datové sady v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)