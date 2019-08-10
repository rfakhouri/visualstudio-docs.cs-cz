---
title: Aktualizace dat pomocí objektu TableAdapter
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 61ebcd6c833b55f0769365b89274e35136c914f9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925351"
---
# <a name="update-data-by-using-a-tableadapter"></a>Aktualizace dat pomocí objektu TableAdapter

Po úpravě a ověření dat ve vaší datové sadě můžete aktualizovaná data odeslat zpět do databáze voláním `Update` metody [TableAdapter](../data-tools/create-and-configure-tableadapters.md). Metoda aktualizuje jedinou datovou tabulku a spustí správný příkaz (INSERT, Update nebo Delete) na základě <xref:System.Data.DataRow.RowState%2A> každého řádku dat v tabulce. `Update` Pokud má datová sada související tabulky, aplikace Visual Studio vygeneruje třídu TableAdapterManager, kterou použijete k provedení aktualizací. Třída TableAdapterManager zajišťuje, že aktualizace budou provedeny ve správném pořadí na základě omezení cizího klíče, které jsou definovány v databázi. Při použití ovládacích prvků vázaných na data vytvoří architektura datové vazby členskou proměnnou třídy TableAdapterManager s názvem tableAdapterManager.

> [!NOTE]
> Když se pokusíte aktualizovat zdroj dat obsahem datové sady, můžete získat chyby. Aby se předešlo chybám, doporučujeme, abyste vložili kód, který volá `Update` metodu adaptéru `try` / `catch` uvnitř bloku.

Přesný postup pro aktualizaci zdroje dat se může lišit v závislosti na obchodních potřebách, ale obsahuje následující kroky:

1. Zavolejte `Update` metodu adaptéru `try` v bloku./ `catch`

2. Pokud je zachycena výjimka, vyhledejte řádek dat, který způsobil chybu.

3. Odsouhlasení problému s datovým řádkem (v případě, že je to možné, nebo zadáním neplatného řádku uživateli pro úpravu) a pak zkuste aktualizaci zopakovat<xref:System.Data.DataRow.HasErrors%2A>( <xref:System.Data.DataTable.GetErrors%2A>,).

## <a name="save-data-to-a-database"></a>Uložení dat do databáze

`Update` Zavolejte metodu TableAdapter. Předejte název tabulky dat obsahující hodnoty, které mají být zapsány do databáze.

### <a name="to-update-a-database-by-using-a-tableadapter"></a>Aktualizace databáze pomocí TableAdapter

- Uzavřete`Update` metodu TableAdapter `try` do bloku./ `catch` Následující příklad ukazuje `Customers` , jak aktualizovat obsah tabulky v `NorthwindDataSet` rámci `try` / `catch` bloku.

     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)