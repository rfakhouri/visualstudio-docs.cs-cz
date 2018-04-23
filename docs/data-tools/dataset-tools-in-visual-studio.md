---
title: Datové sady nástrojů v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.data.DataSet
helpviewer_keywords:
- untyped datasets
- datasets [Visual Basic], extended properties
- typed datasets
- current record in dataset
- XML [Visual Basic], datasets
- DataSet class, about datasets
- unique constraints (datasets)
- data relationships
- parent records in datasets
- extended properties, in typed datasets
- datasets [Visual Basic]
- schemas [Visual Basic], datasets
- datasets [Visual Basic], msprop
- master-detail tables, datasets
- databases [Visual Basic], updating
- msprop
- foreign keys, datasets
- DataSet class
- datasets [Visual Basic], filling
- case sensitivity, datasets
- constraints [Visual Basic], datasets
- child records
- related tables, datasets
- updating datasets, about dataset updates
- data caching, datasets
- DataRelation object, datasets
- untyped datasets, compared to typed datasets
- cache [Visual Studio], datasets
- datasets [Visual Basic], relationships
- related tables
- XML schemas, about XML schemas and datasets
- relationships, datasets
- typed datasets, compared to untyped datasets
- datasets [Visual Basic], populating
- datasets [Visual Basic], namespace
- data adapters, populating datasets
ms.assetid: ee57f4f6-9fe1-4e0a-be9a-955c486ff427
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d4697fb9f0cbc56fef2b27a3fd14a0a91a224b09
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="dataset-tools-in-visual-studio"></a>Datové sady nástrojů v sadě Visual Studio
> [!NOTE]
>  Datové sady a souvisejících tříd se starší verze technologie .NET z časná 2000s, která umožňují aplikacím pracovat s daty v paměti z databáze se odpojené aplikace. Jsou užitečné zejména pro aplikace, které umožňují uživatelům měnit data a zachová tak změny zpět do databáze. I když datové sady ukázala technologie velmi úspěšné, doporučujeme použít rozhraní Entity Framework nové aplikace .NET. Rozhraní Entity Framework poskytuje více fyzických způsob, jak pracovat s tabulková data jako objektové modely a je jednodušší programovací rozhraní.

 Objekt datové sady je objekt v paměti, který je v podstatě zkrácená databáze. Obsahuje objekty DataTable, DataColumn a DataRow, ve kterých můžete ukládat a upravit data z jedné nebo více databází, aniž by bylo nutné udržovat otevřené připojení. Datová sada uchovává informace o změnách svá data, tak, aby aktualizace můžete sledovat a odeslána zpět do databáze, když vaše aplikace bude znovu.

 Datové sady a související třídy jsou definovány v oboru názvů System.Data v knihovně tříd rozhraní .NET Framework. Můžete vytvořit a upravit datové sady dynamicky v kódu. Další informace o tom, jak to udělat najdete v části ADO.NET. V dokumentaci v této části ukazuje, jak pracovat s datovými sadami pomocí sady Visual Studio Designer. Jednou z věcí vědět: datové sady, které jsou vytvářeny pomocí návrháře TableAdapter objekty používat k interakci s databází, zatímco objekty DataAdapter použít datové sady, které jsou vytvářeny prostřednictvím kódu programu. Informace o vytváření datových sad prostřednictvím kódu programu najdete v tématu [DataAdapters a DataReaders](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

 Pokud aplikace potřebuje pouze číst data z databáze, a nebude provádět aktualizace, přidá nebo odstraní, obvykle získáte lepší výkon pomocí DataReader – objekt k načtení dat do objekt obecné seznamu nebo jiné kolekce. Pokud jsou zobrazena data, vám může vytvořit datovou vazbu uživatelské rozhraní ke kolekci.

## <a name="dataset-workflow"></a>Pracovní postup datové sady
 Visual Studio poskytuje mnoho nástrojů pro zjednodušení práce s datovými sadami. Je základní pracovní postup začátku do konce:

-   Použití **zdroj dat** okno Vytvořit novou sadu dat z jednoho nebo více zdrojů dat. Použití **návrháře Dataset** ke konfiguraci datovou sadu a nastavit jeho vlastnosti. Například budete muset zadat tabulky, ze zdroje dat chcete zahrnout a které sloupce z každé tabulky. Zvolte pečlivě kvůli úspoře množství paměti, který bude vyžadovat datovou sadu. Další informace najdete v tématu [vytvořit a nakonfigurovat datové sady](../data-tools/create-and-configure-datasets-in-visual-studio.md).

-   Zadejte relace mezi tabulkami, takže cizí klíče jsou zpracovávány správně. Další informace najdete v tématu [vyplnění datové sady s použitím TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).

-   Použití **Průvodce nastavením TableAdapter** určete dotazu nebo uložené procedury, jež bude naplnění datové sady a jaké databázových operací (aktualizace, odstranění atd.) k implementaci. Další informace naleznete v následujících tématech:

    -   [Vyplnění datové sady s použitím objektů TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)

    -   [Úprava dat v datových sadách](../data-tools/edit-data-in-datasets.md)

    -   [Ověřování dat v datových sadách](../data-tools/validate-data-in-datasets.md)

    -   [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)

-   Dotaz a vyhledávání dat v datové sadě. Další informace najdete v tématu [dotaz datové sady](../data-tools/query-datasets.md). [!INCLUDE[linq_dataset](../data-tools/includes/linq_dataset_md.md)] umožňuje [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/) nad daty v <xref:System.Data.DataSet> objektu. Další informace najdete v tématu [LINQ na DataSet](/dotnet/framework/data/adonet/linq-to-dataset).

-   Použití **zdroje dat** okno pro vytvoření vazby ovládacích prvků uživatelského rozhraní pro datové sady nebo její jednotlivé sloupce a určete sloupce, které mají být uživatele nelze upravit. Další informace najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="datasets-and-n-tier-architecture"></a>Datové sady a N-vrstvá architektura
 Informace o datových sad ve víceúrovňových aplikacích najdete v tématu [pracovat s datovými sadami ve vícevrstvých aplikacích](../data-tools/work-with-datasets-in-n-tier-applications.md).

## <a name="datasets-and-xml"></a>Datové sady a XML
 Informace o převodu datové sady do a ze souboru XML, najdete v článku [data XML pro čtení do datové sady](../data-tools/read-xml-data-into-a-dataset.md) a [uložení datové sady ve formátu XML](../data-tools/save-a-dataset-as-xml.md).

## <a name="see-also"></a>Viz také

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)