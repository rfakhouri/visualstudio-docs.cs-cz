---
title: Přímý přístup k databázi pomocí objektu TableAdapter
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 53d4b2e75be288422300122d5ef9f523068dd9fc
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756451"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>Přímý přístup k databázi pomocí objektu TableAdapter
Kromě `InsertCommand`, `UpdateCommand`, a `DeleteCommand`, TableAdapters jsou vytvořeny pomocí metody, které lze spustit přímo v databázi. Můžete volat tyto metody (`TableAdapter.Insert`, `TableAdapter.Update`, a `TableAdapter.Delete`) k manipulaci s daty přímo v databázi.

 Pokud nechcete vytvořit tyto přímé metody, nastavte TableAdapter `GenerateDbDirectMethods` vlastnost `false` v **vlastnosti** okno. Pokud se všechny dotazy jsou přidány do TableAdapter kromě hlavní dotazů TableAdapter, jsou samostatné dotazy, které tyto negenerovat `DbDirect` metody.

## <a name="send-commands-directly-to-a-database"></a>Odesílat příkazy přímo k databázi
 Volání TableAdapter `DbDirect` metodu, která provede úlohu chcete provést.

#### <a name="to-insert-new-records-directly-into-a-database"></a>Pro vkládání nových záznamů do databáze

-   Volání TableAdapter `Insert` metodu předáním v hodnoty pro každý sloupec jako parametry. Následující postup používá `Region` tabulky v databázi Northwind jako příklad.

    > [!NOTE]
    >  Pokud nemáte k dispozici instance, vytváření instancí TableAdapter, který chcete použít.

     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]

#### <a name="to-update-records-directly-in-a-database"></a>K aktualizaci záznamů přímo v databázi

-   Volání TableAdapter `Update` metodu předáním v nové a původní hodnoty pro každý sloupec jako parametry.

    > [!NOTE]
    >  Pokud nemáte k dispozici instance, vytváření instancí TableAdapter, který chcete použít.

     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-csharp[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]

#### <a name="to-delete-records-directly-from-a-database"></a>Chcete-li odstranit záznamy přímo z databáze

-   Volání TableAdapter `Delete` metodu předáním v hodnoty pro každý sloupec jako parametry `Delete` metoda. Následující postup používá `Region` tabulky v databázi Northwind jako příklad.

    > [!NOTE]
    >  Pokud nemáte k dispozici instance, vytváření instancí TableAdapter, který chcete použít.

     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-csharp[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]

## <a name="see-also"></a>Viz také:

- [Vyplnění datové sady s použitím objektů TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)