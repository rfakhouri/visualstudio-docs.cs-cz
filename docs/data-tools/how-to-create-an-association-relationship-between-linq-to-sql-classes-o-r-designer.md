---
title: Vytvoření vztahu mezi třídy LINQ to SQL pomocí Návrháře relací objektů
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 6b6f0b1f3afec1231778a54c82422d6761995eb1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402805"
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>Postupy: Vytvoření přidružení mezi třídy LINQ to SQL (O/R Designer)
Přidružení mezi třídami entit v [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] jsou podobná relace mezi tabulkami v databázi. Můžete vytvořit přidružení mezi třídami entit pomocí **Editor asociace** dialogové okno.

Při použití musíte vybrat třídu nadřazené a podřízené třídy **Editor asociace** dialogové okno Vytvoření přidružení. Nadřazená třída je třída entity, která obsahuje primární klíč. podřízené třídy je třída entity, která obsahuje cizího klíče. Například, pokud tříd entit byly vytvořeny, která je namapována na `Northwind Customers` a `Orders` tabulky, `Customer` třídy by nadřazené třídy a `Order` třída by být podřízené třídy.

> [!NOTE]
> Při přetažení tabulky z **Průzkumníka serveru** nebo **Průzkumník databáze** na **Návrhář relací objektů** (**O/R Designer**), přidružení se automaticky vytvoří podle existující relace cizího klíče v databázi.

## <a name="association-properties"></a>Vlastnosti přidružení
Po vytvoření asociace, když vyberete přidružení v **O/R Designer**, existuje několik konfigurovatelných vlastností v **vlastnosti** okna. (Přidružení je řádek mezi souvisejícími třídami.) Následující tabulka obsahuje popis vlastností asociace.

|Vlastnost|Popis|
|--------------|-----------------|
|**Kardinalita**|Určuje, zda že asociace je 1 n nebo 1: 1.|
|**Podřízená vlastnost**|Určuje, jestli se má vytvořit vlastnost u nadřazené, který je kolekce nebo odkaz na podřízené záznamy na straně cizího klíče asociace. Například v přidružení mezi `Customer` a `Order`, pokud **vlastnost podřízeného** je nastavena na **True**, vlastnost s názvem `Orders` vytvořené v nadřazené třídy.|
|**Nadřazená vlastnost**|Vlastnost u podřízené třídy, která odkazuje na přidruženou nadřazenou třídu. Například v přidružení mezi `Customer` a `Order`, vlastnost s názvem `Customer` odkazující přidružené zákazníka pro objednávku se vytvoří na `Order` třídy.|
|**Zúčastněné vlastnosti**|Zobrazí vlastnosti přidružení a poskytuje **tlačítko se třemi tečkami** tlačítko (...), která znovu se otevře **Editor asociace** dialogové okno.|
|**Jedinečný**|Určuje, jestli mají sloupce cizího omezení jedinečnosti.|

## <a name="to-create-an-association-between-entity-classes"></a>Vytvoření přidružení mezi třídami entit

1. Klikněte pravým tlačítkem na třídu entity, která představuje nadřazené třídu v přidružení, přejděte na **přidat**a potom klikněte na tlačítko **přidružení**.

2. Ověřte, že správné **nadřazené třídu** výběru v **Editor asociace** dialogové okno.

3. Vyberte **podřízené třídy** v poli se seznamem.

4. Vyberte **vlastnosti přidružení** , které se týkají třídy. Obvykle to se mapuje na vztah cizího klíče definovanými v databázi. Například v `Customers` a `Orders` přidružení, **vlastnosti přidružení** jsou `CustomerID` pro každou třídu.

5. Klikněte na tlačítko **OK** vytváření přidružení.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytvoření LINQ na třídy SQL](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Metody DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md)
- [Postupy: Znázornění primárních klíčů](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)