---
title: Nástroje datové sady
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
f1_keywords:
- vs.data.DataSet
dev_langs:
- VB
- CSharp
- C++
- aspx
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
caps.latest.revision: 53
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 553d4f7ca61bbc01e72e8735b0007d2f08876e71
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59666504"
---
# <a name="dataset-tools-in-visual-studio"></a>Nástroje datové sady v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

POZNÁMKA:]
>  Datové sady a související třídy jsou starší verze technologie .NET v rané fázi 2000s, která umožňují aplikacím pro práci s daty v paměti z databáze se odpojené aplikace. Jsou zvláště užitečné pro aplikace, které umožňují uživatelům upravovat data a zachová tak změny zpět do databáze. I když datové sady ukázaly jako velmi úspěšná technologie, doporučujeme použít rozhraní Entity Framework nové aplikace .NET. Entity Framework poskytuje přirozenější způsob, jak fungují s tabulkovými daty jako objektové modely a je jednodušší programovací rozhraní.

 Objekt DataSet je objekt v paměti, který je v podstatě zkrácené databáze. Obsahuje objekty DataTable, objekt DataColumn a objekt DataRow, ve kterých můžete ukládat a upravit data z jedné nebo víc databází, aniž byste museli udržovat otevřené připojení. Datovou sadu uchovává informace o změny dat, takže aktualizace můžete sledovat a odesílá zpět do databáze, když vaše aplikace bude znovu připojeny.

 Datové sady a související třídy jsou definovány v oboru názvů System.Data v knihovně tříd rozhraní .NET Framework. Můžete vytvářet a upravovat datové sady dynamicky v kódu. Další informace o tom, jak to udělat najdete v článku ADO.NET. Dokumentace v této části ukazuje, jak pracovat s datovými sadami pomocí návrháře sady Visual Studio. Jednou z věcí vědět: datových sad, které se provádějí přes návrháři použít objekty TableAdapter interakci s databází, zatímco datové sady, které probíhají prostřednictvím kódu programu pomocí adaptéru dat objektů. Informace o vytváření datových sad prostřednictvím kódu programu najdete v tématu [adaptéry a čtečky dat](http://msdn.microsoft.com/library/cc952ca2-ec19-46ab-9189-15174b52cb74).

 Pokud vaše aplikace je potřeba jenom číst data z databáze a nebude provádět aktualizace, přidá nebo odstraní, obvykle získáte lepší výkon pomocí objektu DataReader k načtení dat do obecného seznamu objektů nebo jiného objektu kolekce. Pokud je zobrazení dat, je můžete vytvořte datovou vazbu uživatelského rozhraní do kolekce.

## <a name="dataset-workflow"></a>Pracovní postup datové sady
 Visual Studio poskytuje celou řadu nástrojů pro zjednodušení práce s datovými sadami. Je základní pracovní postup začátku do konce:

-   Použití **zdroj dat** okno pro vytvoření nové datové sady z jednoho nebo více zdrojů dat. Použití **Návrhář Dataset** konfigurace datové sady a nastavte jeho vlastnosti. Například musíte zadat tabulky ze zdroje dat chcete zahrnout a které sloupce z každé tabulky. Pečlivě kvůli úspoře množství paměti, který bude vyžadovat datové sady. Další informace najdete v tématu [vytvoření a konfigurace datové sady](../data-tools/create-and-configure-datasets-in-visual-studio.md).

-   Zadejte relace mezi tabulkami, tak, že jsou správně zpracovány cizí klíče. Další informace najdete v tématu [vyplnění datové sady s použitím objektů TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md).

-   Použití **Průvodce nastavením TableAdapter** zadat dotaz nebo uloženou proceduru, která bude při naplnění datové sady a jaké operace databáze (update, delete a podobně) k implementaci. Další informace najdete v těchto tématech:

    -   [Vyplnění datových sad pomocí objektů TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)

    -   [Úprava dat v datových sadách](../data-tools/edit-data-in-datasets.md)

    -   [Ověřování dat v datových sadách](../data-tools/validate-data-in-datasets.md)

    -   [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)

-   Dotazování a hledání dat v datové sadě. Další informace najdete v tématu [dotazování datových sad](../data-tools/query-datasets.md). [!INCLUDE[linq_dataset](../includes/linq-dataset-md.md)] umožňuje [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) nad daty v <xref:System.Data.DataSet> objektu. Další informace najdete v tématu [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).

-   Použití **zdroje dat** okno pro vytvoření vazby ovládacích prvků uživatelského rozhraní datové sady nebo jeho jednotlivé sloupce a chcete-li určit sloupce, které se uživatel upravovat. Další informace najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="datasets-and-n-tier-architecture"></a>Datové sady a N-vrstvou architekturu
 Informace o datových sad v N-vrstvé aplikace najdete v tématu [práce s datovými sadami ve vícevrstvých aplikacích](../data-tools/work-with-datasets-in-n-tier-applications.md).

## <a name="datasets-and-xml"></a>Datové sady a XML
 Informace o převodu datových sad do a ze souboru XML, naleznete v tématu [XML pro čtení dat do datové sady](../data-tools/read-xml-data-into-a-dataset.md) a [uložení datové sady ve formátu XML](../data-tools/save-a-dataset-as-xml.md).

## <a name="see-also"></a>Viz také
 [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
