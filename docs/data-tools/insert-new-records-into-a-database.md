---
title: Vkládání nových záznamů do databáze
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, inserting new records into
- data [Visual Studio], saving
- databases, inserting new records into
- records, inserting
- saving data
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 515140564d9523c9f1dfe6b3b904aaa3b37df45f
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089568"
---
# <a name="insert-new-records-into-a-database"></a>Vkládání nových záznamů do databáze
Chcete-li vkládání nových záznamů do databáze, můžete použít `TableAdapter.Update` metoda nebo jeden z TableAdapter DBDirect – metody (konkrétně `TableAdapter.Insert` metoda). Další informace najdete v tématu [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

 Pokud vaše aplikace nepoužívá TableAdapters, můžete použít příkaz objekty (například <xref:System.Data.SqlClient.SqlCommand>) k vkládání nových záznamů do databáze.

 Pokud vaše aplikace používá k ukládání dat datové sady, použijte `TableAdapter.Update` metoda. `Update` Metoda odešle všechny změny (aktualizace, vložení a odstranění) do databáze.

 Pokud vaše aplikace používá objekty k ukládání dat, nebo pokud chcete ovládat přesněji vytváření nových záznamů v databázi, použijte `TableAdapter.Insert` metoda.

 Pokud vaše TableAdapter nemá `Insert` metoda, znamená to, že je buď TableAdapter nakonfigurované na použití uložené procedury nebo jeho `GenerateDBDirectMethods` je nastavena na `false`. Zkuste nastavit TableAdapter `GenerateDBDirectMethods` vlastnost `true` uvnitř **návrháře Dataset**a potom uložte datovou sadu. Tímto se znova vygeneruje TableAdapter. Pokud TableAdapter stále nemá `Insert` metoda, tabulka pravděpodobně neposkytuje dostatek informací o schématu k rozlišení jednotlivých řádků (například může zde být nastavený žádný primární klíč tabulky).

## <a name="insert-new-records-by-using-tableadapters"></a>Vkládání nových záznamů pomocí TableAdapters
 TableAdapters poskytují různé způsoby vkládání nových záznamů do databáze, v závislosti na požadavcích vaší aplikace.

 Pokud vaše aplikace používá k ukládání dat datové sady, můžete jednoduše přidat nové záznamy na požadovanou <xref:System.Data.DataTable> v datové sadě a pak volání `TableAdapter.Update` metoda. `TableAdapter.Update` Metoda odešle všechny změny v <xref:System.Data.DataTable> do databáze (včetně upravené a odstraněné záznamy).

### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterupdate-method"></a>Chcete-li vkládání nových záznamů do databáze pomocí TableAdapter.Update – metoda

1.  Přidání nových záznamů do požadované <xref:System.Data.DataTable> tak, že vytvoříte novou <xref:System.Data.DataRow> a jejím přidáním do <xref:System.Data.DataTable.Rows%2A> kolekce.

2.  Po přidání nové řádky do <xref:System.Data.DataTable>, volání `TableAdapter.Update` metoda. Můžete řídit množství dat k aktualizaci předáním buď celou <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, pole <xref:System.Data.DataRow>s nebo jedné <xref:System.Data.DataRow>.

 Následující kód ukazuje, jak přidat nový záznam pro <xref:System.Data.DataTable> a pak zavolají `TableAdapter.Update` metoda uložit do databáze nový řádek. (Tento příklad používá `Region` tabulky v databázi Northwind.)

 [!code-vb[VbRaddataSaving#14](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_1.vb)]
 [!code-csharp[VbRaddataSaving#14](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_1.cs)]

### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterinsert-method"></a>Chcete-li vkládání nových záznamů do databáze pomocí TableAdapter.Insert – metoda
Pokud vaše aplikace používá objekty k ukládání dat, můžete použít `TableAdapter.Insert` metodu pro vytvoření nové řádky přímo v databázi. `Insert` Metoda přijímá jednotlivé hodnoty pro každý sloupec jako parametry. Volání metody vloží nový záznam do databáze s předané hodnoty parametru.

- Volání TableAdapter `Insert` metodu předáním v hodnoty pro každý sloupec jako parametry.

 Následující postup ukazuje, jak pomocí `TableAdapter.Insert` metoda vložení řádků. Tento příklad vkládá data do `Region` tabulky v databázi Northwind.

 > [!NOTE]
 >  Pokud nemáte k dispozici instance, vytváření instancí TableAdapter, kterou chcete použít.

 [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_2.vb)]
 [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_2.cs)]

## <a name="insert-new-records-by-using-command-objects"></a>Vkládání nových záznamů pomocí objekty příkazu
Nové záznamy můžete vložit přímo do databáze pomocí příkazu objekty.

### <a name="to-insert-new-records-into-a-database-by-using-command-objects"></a>Chcete-li vkládání nových záznamů do databáze pomocí příkazu objektů

-   Vytvořit nový objekt příkazu a poté nastavte její `Connection`, `CommandType`, a `CommandText` vlastnosti.

 Následující příklad ukazuje vložení záznamu do databáze pomocí příkazu objektu. Vloží data do `Region` tabulky v databázi Northwind.

 [!code-vb[VbRaddataSaving#16](../data-tools/codesnippet/VisualBasic/insert-new-records-into-a-database_3.vb)]
 [!code-csharp[VbRaddataSaving#16](../data-tools/codesnippet/CSharp/insert-new-records-into-a-database_3.cs)]

## <a name="net-framework-security"></a>zabezpečení v rozhraní .NET Framework
 Musíte mít přístup k databázi, kterou se pokoušíte připojit k, jakož i oprávnění k provedení vloží do požadované tabulky.

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)