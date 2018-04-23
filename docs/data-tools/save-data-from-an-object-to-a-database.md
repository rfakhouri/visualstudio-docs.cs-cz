---
title: Uložení dat z objektu do databáze
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data access [Visual Studio], objects
- saving data
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 42bbdb5cff0d244701e28730ab6b12d70b49a920
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="save-data-from-an-object-to-a-database"></a>Uložení dat z objektu do databáze
Data můžete uložit v objektech k databázi předáním hodnoty z objektu do jednoho z TableAdapter DBDirect – metody (například `TableAdapter.Insert`). Další informace najdete v tématu [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

 K uložení dat z kolekce objektů, projděte kolekci objektů (například smyčku pro další) a odesílají hodnoty pro každý objekt do databáze pomocí jedné z TableAdapter DBDirect – metody.

 DBDirect – metody jsou ve výchozím nastavení vytvoří na TableAdapter, který můžete spustit přímo v databázi. Tyto metody lze volat přímo a nevyžadují <xref:System.Data.DataSet> nebo <xref:System.Data.DataTable> objekty sloučit změny k odeslání aktualizací do databáze.

> [!NOTE]
>  Konfiguraci TableAdapter, hlavní dotaz musí poskytnout dostatek informací pro metody DBDirect, který se má vytvořit. Například pokud TableAdapter je nakonfigurovaný k dotazování na data z tabulky, který nemá definovaný sloupec primárního klíče, je negeneruje DBDirect – metody.

|TableAdapter DBDirect – metoda|Popis|
|----------------------------------|-----------------|
|`TableAdapter.Insert`|Přidá nové záznamy k databázi a umožňuje předat hodnoty jednotlivých sloupců jako parametry metody.|
|`TableAdapter.Update`|Aktualizuje existující záznamy v databázi. `Update` Metoda přebírá původní a nové sloupce hodnoty jako parametry metody. Původní hodnoty, které se používají pro vyhledání původní záznam a s novými hodnotami, které se používají k aktualizaci záznamů.<br /><br /> `TableAdapter.Update` Metoda slouží také k sjednotit provedením změn v datové sadě zpět do databáze <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, nebo pole <xref:System.Data.DataRow>s jako parametry metody.|
|`TableAdapter.Delete`|Odstraní existující záznamy z databáze založené na původní hodnoty ve sloupcích předána jako parametry metody.|

### <a name="to-save-new-records-from-an-object-to-a-database"></a>Uložení nové záznamy z objektu do databáze

-   Vytvořte záznamy předáním hodnoty, které mají `TableAdapter.Insert` metoda.

     Následující příklad vytvoří nový záznam v `Customers` předáním hodnoty v tabulce `currentCustomer` do objektu `TableAdapter.Insert` metoda.

     [!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_1.cs)]
     [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_1.vb)]

### <a name="to-update-existing-records-from-an-object-to-a-database"></a>Chcete-li aktualizovat existující záznamy z objektu do databáze

-   Upravit záznamy voláním `TableAdapter.Update` metoda předávání v nové hodnoty, kde aktualizují záznam a předávání v původní hodnoty najít záznam.

    > [!NOTE]
    >  Váš objekt musí udržovat původní hodnoty, aby bylo možné předat je do `Update` metoda. Tento příklad používá vlastnosti `orig` předpona k uložení původní hodnoty.

     Následující příklad aktualizuje existující záznam v `Customers` předáním nové a původní hodnoty v tabulce `Customer` do objektu `TableAdapter.Update` metoda.

     [!code-csharp[VbRaddataSaving#24](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_2.cs)]
     [!code-vb[VbRaddataSaving#24](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_2.vb)]

### <a name="to-delete-existing-records-from-a-database"></a>Chcete-li odstranit existující záznamy z databáze

-   Odstranit záznamy voláním `TableAdapter.Delete` metoda a předávání v původní hodnoty najít záznam.

    > [!NOTE]
    >  Váš objekt musí udržovat původní hodnoty, aby bylo možné předat je do `Delete` metoda. Tento příklad používá vlastnosti `orig` předpona k uložení původní hodnoty.

     Následující příklad odstraní záznam `Customers` předáním původní hodnoty v tabulce `Customer` do objektu `TableAdapter.Delete` metoda.

     [!code-csharp[VbRaddataSaving#25](../data-tools/codesnippet/CSharp/save-data-from-an-object-to-a-database_3.cs)]
     [!code-vb[VbRaddataSaving#25](../data-tools/codesnippet/VisualBasic/save-data-from-an-object-to-a-database_3.vb)]

## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework
 Musíte mít oprávnění k provedení vybrané příkaz INSERT, UPDATE nebo DELETE pro tabulku v databázi.

## <a name="see-also"></a>Viz také

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)