---
title: Aktualizace dat pomocí TableAdapter | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 30d1fd3ee211d6b30f435104a2e2f9b42ed100c0
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65692350"
---
# <a name="update-data-by-using-a-tableadapter"></a>Aktualizace dat pomocí objektu TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po dat ve vaší datové sadě byl změněn a ověřit, můžete odeslat aktualizovaná data zpět do volání databaseby `Update` metody třídy TableAdapter. `Update` Metodu aktualizace jedné tabulky datového a spustí správný příkaz (vložení, aktualizace nebo odstranění) na základě <xref:System.Data.DataRow.RowState%2A> každého řádku dat v tabulce. Když datové sady má související tabulky, Visual Studio vygeneruje třídy TableAdapterManager, které umožňují provádět aktualizace. Třída TableAdapterManager zajistí, že jsou ve správném pořadí podle omezení cizího klíče, které jsou definovány v databázi provedeny aktualizace. Při použití ovládacích prvků vázaných na data, architektura vázání dat vytvoří členské proměnné třídy TableAdapterManager volá tableAdapterManager. Další informace najdete v tématu [přehled hierarchické aktualizace](https://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6).  
  
> [!NOTE]
> Při pokusu aktualizovat zdroj dat s obsahem datové sady, může docházet k chybám. Aby nedocházelo k chybám, doporučujeme, abyste vložit kód, který volá adaptéru `Update` metodu `try` / `catch` bloku.  
  
 Přesný postup pro aktualizaci zdroje dat se může lišit v závislosti na obchodní potřeby, ale zahrnuje následující kroky:  
  
1. Volání `Update` metoda `try` / `catch` bloku.  
  
2. Pokud je výjimka zachycena, vyhledejte řádek dat, která způsobila chybu. Další informace najdete v tématu [jak: Vyhledání řádků s chybami](https://msdn.microsoft.com/library/1fa907c5-fe66-4f29-a253-2b97b900050c).  
  
3. Sjednotit problém v datech řádku (prostřednictvím kódu programu, pokud je to možné, nebo tím, že předloží neplatný řádek pro uživatele pro úpravy) a akci opakujte aktualizaci (<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>).  
  
## <a name="savedata-to-a-database"></a>SaveData k databázi  
 Volání `Update` metody třídy TableAdapter. Předejte název tabulky dat, který obsahuje hodnoty, které mají být zapsána do databáze.  
  
#### <a name="to-update-a-database-by-using-a-tableadapter"></a>Chcete-li aktualizovat databázi pomocí TableAdapter  
  
- Uzavřete objektu TableAdapter`Update` metoda `try` / `catch` bloku. Následující příklad ukazuje, jak aktualizovat obsah `Customers` tabulku v `NorthwindDataSet` zevnitř `try` / `catch` bloku.  
  
     [!code-csharp[VbRaddataSaving#9](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#9)]
     [!code-vb[VbRaddataSaving#9](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#9)]  
  
## <a name="see-also"></a>Viz také  
 [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
