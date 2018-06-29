---
title: 'Postupy: vytvoření LINQ na třídy SQL, které jsou namapované na tabulky a zobrazení (Návrhář O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0fb78bbc-7a78-4ab4-b32f-85ece912e660
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 11fb4265047387e30327bbbe17c9babf1f23ec61
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089322"
---
# <a name="how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-or-designer"></a>Postupy: vytvoření LINQ na třídy SQL, které jsou namapované na tabulky a zobrazení (Návrhář relací objektů)
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy, které jsou namapované na databázových tabulek a zobrazení, se nazývají *tříd entit*. Třídy entita se mapuje na záznam, kdežto jednotlivé vlastnosti třídy entity mapování na jednotlivé sloupce, které tvoří záznam. Vytváření tříd entit, které jsou založeny na databázových tabulek nebo zobrazení tak, že přetáhnete tabulky a zobrazení z **Průzkumníka serveru** nebo **Průzkumník databáze** na [technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md). **Návrhář relací objektů** vygeneruje třídy a použije konkrétní [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] atributy povolit [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] funkce (datové komunikace a možnosti Úpravy <xref:System.Data.Linq.DataContext>). Podrobné informace o [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídách naleznete v tématu [technologii LINQ to SQL objektový model](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model).

> [!NOTE]
>  **Návrhář relací objektů** je relační mapper jednoduchého objektu, protože ji podporuje jenom relace 1:1 mapování. Jinými slovy třídu entity může mít pouze vztah mapování 1:1 s databázové tabulky nebo zobrazení. Komplexní mapování, jako je například k několika tabulkám, mapování třídu entity není podporována. Však můžete namapovat třídu entity zobrazení, které spojuje více souvisejících tabulek.

## <a name="create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>Vytvořit LINQ pro třídy SQL, které jsou mapované na databázových tabulek a zobrazení
 Přetahování tabulky nebo zobrazení, z **Průzkumníka serveru** nebo **Průzkumník databáze** na **Návrhář relací objektů** vytvoří tříd entit kromě <xref:System.Data.Linq.DataContext> metody, slouží k provádění aktualizací.

 Ve výchozím nastavení [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] runtime vytvoří logika uložíte změny z třídy aktualizovat entity zpět do databáze. Tato logika je založena na schéma tabulky (definice sloupců a informace o primárním klíči). Pokud nechcete, aby toto chování, můžete nakonfigurovat třídu entity k pomocí uložené procedury provádět vložení, aktualizace a odstranění místo použití výchozí [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] modul runtime chování. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>Chcete-li vytvořit LINQ na SQL třídy, které jsou mapované na databázových tabulek a zobrazení

1.  V **Server** nebo **Průzkumník databáze**, rozbalte položku **tabulky** nebo **zobrazení** a vyhledat databázové tabulky nebo zobrazení, kterou chcete použít v vaší aplikace.

2.  Přetáhněte v tabulce nebo zobrazení na **Návrhář relací objektů**.

     Třídu entity se vytvoří a zobrazí se na návrhovou plochu. Třída entity má vlastnosti, které mapují na sloupce ve vybrané tabulce nebo zobrazení.

## <a name="create-an-object-data-source-and-display-the-data-on-a-form"></a>Vytvoření objektu zdroje dat a zobrazení dat ve formuláři
 Po vytvoření tříd entit s použitím **Návrhář relací objektů**, můžete vytvořit zdroj dat objektu a naplnit [okna zdroje dat](add-new-data-sources.md) s třídami entity.

### <a name="to-create-an-object-data-source-based-on-linq-to-sql-entity-classes"></a>Chcete-li vytvořit zdroj dat objektu podle LINQ na SQL entity třídy

1.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení** k sestavení projektu.

2.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.

3.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.

4.  Klikněte na tlačítko **objekt** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.

5.  Rozbalte uzly a vyhledejte a vyberte třídu.

    > [!NOTE]
    >  Pokud **zákazníka** třída není k dispozici, ukončete průvodce, sestavte projekt a opakujte akci.

6.  Klikněte na tlačítko **Dokončit** vytvoření zdroje dat a přidat **zákazníka** třídu entity k **zdroje dat** okno.

7.  Přetáhnout položky z **zdroje dat** okna do formuláře.

## <a name="see-also"></a>Viz také:

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytvoření LINQ na SQL třídy (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Metody DataContext (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md)
- [Postupy: vytvoření metody DataContext namapované na uložené procedury a funkce (Návrhář relací objektů)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [Technologie LINQ to SQL objektový model](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model)
- [Návod: Přizpůsobení vložit, aktualizovat a odstraňovat chování tříd entit](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [Postupy: vytvoření přidružení (vztah) mezi technologie LINQ to SQL třídy (Návrhář relací objektů)](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)