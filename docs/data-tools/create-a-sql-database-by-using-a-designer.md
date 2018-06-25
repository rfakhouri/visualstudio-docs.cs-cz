---
title: Vytvoření souboru databáze a použití Návrháře tabulky v sadě Visual Studio
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- database tables, creating
- database files, creating
- table designer
ms.assetid: 99c2b06f-47aa-414e-8057-a3453712fd23
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5d21ba3f239bb4c5e3fdd1ba717b1288956b8550
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756152"
---
# <a name="create-a-database-and-add-tables-in-visual-studio"></a>Vytvoření databáze a přidání tabulek v sadě Visual Studio
Visual Studio můžete použít k vytváření a aktualizaci místního databázového souboru v SQL serveru Express LocalDB. Můžete také vytvořit databázi spuštěním příkazů Transact-SQL v **Průzkumník objektů systému SQL Server** okno nástroje v sadě Visual Studio. V tomto tématu, vytvoříme *.mdf* souboru a přidejte tabulkami a klíči pomocí Návrháře tabulky.

## <a name="prerequisites"></a>Požadavky
Pro dokončení tohoto návodu, musíte mít volitelné **úložiště dat a zpracování** zatížení, které jsou nainstalované v sadě Visual Studio. K její instalaci, otevřete **instalační program Visual Studio** a zvolte **úlohy** kartě. V části **Web a Cloud**, zvolte **úložiště dat a zpracování**. Vyberte **upravit** tlačítko zatížení přidat do sady Visual Studio.

## <a name="create-a-project-and-a-local-database-file"></a>Vytvoření projektu a místního databázového souboru

### <a name="to-create-a-project-and-a-database-file"></a>Vytvoření projektu a databázového souboru
1.  Vytvoření projektu Windows Forms, který je pojmenován `SampleDatabaseWalkthrough`.

2.  Na panelu nabídek vyberte **projektu** > **přidat novou položku**.

3.  V seznamu šablon položek, posuňte se dolů a vyberte **databáze založené na službě**.

     ![Dialogové okno šablony položek](../data-tools/media/raddata-vsitemtemplates.png)

4.  Název databáze **SampleDatabase**a pak vyberte **přidat** tlačítko.

### <a name="to-add-a-data-source"></a>Chcete-li přidat zdroje dat
5.  Pokud **zdroje dat** okno není otevřený, otevřete ho tak, že vyberete **Shift**+**Alt**+**D** klíče nebo na řádku nabídek vyberte **zobrazení** > **ostatní okna** > **zdroje dat**.

6.  V **zdroje dat** vyberte **přidat nový zdroj dat** odkaz.

    **Průvodce konfigurací zdroje dat** otevře.

7. Na **zvolte typ zdroje dat** vyberte **databáze** a potom vyberte **Další**.

8. Na **vyberte Model databáze** vyberte **Další** přijměte výchozí nastavení (datové sady).

9. Na **vybrat datové připojení** vyberte **SampleDatabase.mdf** souboru v rozevíracím seznamu a potom vyberte **Další**.

10. Na **uložit připojovací řetězec do konfiguračního souboru aplikace** vyberte **Další**.

11. Jeden **zvolte databázové objekty** stránky, zobrazí se zpráva, že databáze neobsahuje žádné objekty. Zvolte **Dokončit**.

### <a name="to-view-properties-of-the-data-connection"></a>Chcete-li zobrazit vlastnosti datového připojení
Připojovací řetězec pro můžete zobrazit *SampleDatabase.mdf* souboru tak, že otevřete okno Vlastnosti datového připojení:

-   V sadě Visual Studio, vyberte **zobrazení** > **Průzkumník objektů systému SQL Server** Pokud toto okno už není otevřený. Otevřete okno Vlastnosti rozšířením **připojení dat** uzlu, na místní nabídku pro otevření *SampleDatabase.mdf*a potom vyberete **vlastnosti**.

-   Alternativně můžete vybrat **zobrazení** > **Průzkumníka serveru**, pokud toto okno už není otevřený. Otevřete okno Vlastnosti rozšířením **datová připojení** uzlu. Otevřete místní nabídku pro *SampleDatabase.mdf*a potom vyberte **vlastnosti**.

## <a name="create-tables-and-keys-by-using-table-designer"></a>Vytvoření tabulky a klíče pomocí Návrháře tabulky
V této části vytvoříte dvě tabulky, primární klíč v každé tabulce a pár řádků ukázková data. Pokud vytvoříte cizí klíč, který chcete určit, jak se záznamy v jedné tabulce odpovídají záznamy v druhé tabulce.

### <a name="to-create-the-customers-table"></a>Vytvoření tabulky Zákazníci
1.  V **Průzkumníka serveru** nebo **Průzkumník objektů systému SQL Server**, rozbalte **připojení dat** uzel a potom rozbalte **SampleDatabase.mdf**uzlu.

2.  Otevřete místní nabídku pro **tabulky**a potom vyberte **přidat novou tabulku**.

     **Návrháře tabulky** otevře a zobrazuje mřížka s řádek jeden výchozí, což představuje jeden sloupec v tabulce, které vytváříte. Přidáním řádků do mřížky přidáte další sloupce v tabulce.

3.  V mřížce přidejte řádek pro každou z následujících položek:

    |Název sloupce|Datový typ|Povolit hodnoty NULL|
    |-----------------|---------------|-----------------|
    |`CustomerID`|`nchar(5)`|Nepravda (nezaškrtnuto)|
    |`CompanyName`|`nvarchar(50)`|Nepravda (nezaškrtnuto)|
    |`ContactName`|`nvarchar (50)`|Pravda (zaškrtnuto)|
    |`Phone`|`nvarchar (24)`|Pravda (zaškrtnuto)|

4.  Otevřete místní nabídku pro `CustomerID` řádek a potom vyberte **nastavit primární klíč**.

5.  Otevřete místní nabídku pro výchozí řádek a pak vyberte **odstranit**.

6.  Pojmenujte tabulku Zákazníci prostřednictvím aktualizace prvního řádku v podokně se skriptem tak, aby odpovídala následující ukázce:

    ```sql
    CREATE TABLE [dbo].[Customers]
    ```

    Měli byste vidět zhruba takhle:

    ![Návrhář tabulky](../data-tools/media/raddata-table-designer.png)

7.  V levém horním rohu **návrháře tabulky**, vyberte **aktualizace** tlačítko.

8.  V **aktualizace databáze Preview** dialogové okno, vyberte **aktualizace databáze** tlačítko.

    Vaše změny jsou uloženy do lokálního databázového souboru.

### <a name="to-create-the-orders-table"></a>Vytvoření tabulky objednávek
1.  Přidejte další tabulku a potom přidejte řádek pro každou položku v následující tabulce:

    |Název sloupce|Datový typ|Povolit hodnoty NULL|
    |-----------------|---------------|-----------------|
    |`OrderID`|`int`|Nepravda (nezaškrtnuto)|
    |`CustomerID`|`nchar(5)`|Nepravda (nezaškrtnuto)|
    |`OrderDate`|`datetime`|Pravda (zaškrtnuto)|
    |`OrderQuantity`|`int`|Pravda (zaškrtnuto)|

2.  Nastavit **OrderID** jako primární klíč a pak odstraňte výchozí řádek.

3.  Pojmenujte tabulku Objednávky prostřednictvím aktualizace prvního řádku v podokně se skriptem tak, aby odpovídala následující ukázce:

    ```sql
    CREATE TABLE [dbo].[Orders]
    ```

4.  V levém horním rohu **návrháře tabulky**, vyberte **aktualizace** tlačítko.

5.  V **aktualizace databáze Preview** dialogové okno, vyberte **aktualizace databáze** tlačítko.

    Vaše změny jsou uloženy do lokálního databázového souboru.

### <a name="to-create-a-foreign-key"></a>Vytvoření cizího klíče
1.  V podokně kontext na pravé straně mřížky otevřete místní nabídku pro **cizí klíče**a potom vyberte **přidat nový cizí klíč**, jak ukazuje následující obrázek.

     ![Přidání cizí klíče v Návrháři tabulky](../data-tools/media/foreignkey.png)

2.  Do textového pole nahradit **ToTable** s `Customers`.

3.  V podokně T-SQL aktualizujte poslední řádek tak, aby odpovídala následující ukázka:

    ```sql
    CONSTRAINT [FK_Orders_Customers] FOREIGN KEY ([CustomerID]) REFERENCES [Customers]([CustomerID])
    ```

4.  V levém horním rohu **návrháře tabulky**, vyberte **aktualizace** tlačítko.

5.  V **aktualizace databáze Preview** dialogové okno, vyberte **aktualizace databáze** tlačítko.

    Vaše změny jsou uloženy do lokálního databázového souboru.

## <a name="populate-the-tables-with-data"></a>Naplnění tabulky s daty

### <a name="to-populate-the-tables-with-data"></a>Naplnění tabulek daty

1.  V **Průzkumníka serveru** nebo **Průzkumník objektů systému SQL Server**, rozbalte uzel v ukázkové databázi.

2.  Otevřete místní nabídku pro **tabulky** uzlu, vyberte **aktualizovat**a potom rozbalte **tabulky** uzlu.

3.  Otevřete místní nabídku pro tabulku zákazníků a pak vyberte **zobrazit Data tabulky**.

4.  Přidáte libovolnou data, která chcete pro některé zákazníky.

    Jako ID zákazníka můžete zadat libovolných pět znaků, ale vyberte alespoň jedno ID takové, které si zapamatujete, abyste je mohli použít později v tomto postupu.

5.  Otevřete místní nabídku pro tabulku objednávky a pak vyberte **zobrazit Data tabulky**.

6.  Přidáte data pro některé objednávky.

    > [!IMPORTANT]
    > Ujistěte se, zda jsou všechny ID pořadí a počty pořadí celá čísla a to každé ID zákazníka hodnotu, která jste zadali v **CustomerID** sloupec tabulky zákazníků.

7.  Na panelu nabídek vyberte **soubor** > **Uložit vše**.

## <a name="see-also"></a>Viz také:

- [Přístup k datům v sadě Visual Studio](accessing-data-in-visual-studio.md)