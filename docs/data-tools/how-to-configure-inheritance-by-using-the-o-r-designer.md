---
title: 'Postupy: Konfigurace dědičnosti pomocí Návrháře relací –'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e594af12-e777-434a-bc08-7dd2dac84cdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 2a68101b6090a20526088309a441956a68e875e9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014663"
---
# <a name="how-to-configure-inheritance-by-using-the-or-designer"></a>Postupy: Konfigurace dědičnosti pomocí Návrháře relací objektů
**Návrhář relací objektů** (**O/R Designer**) podporují koncept dědičnosti jedné tabulky, jak často je implementován v relačních systémech. V dědičnosti jedné tabulky je izolované databáze tabulku, která obsahuje pole pro informace o nadřazené i podřízené informace. Sloupec diskriminátoru s relačními daty, obsahuje hodnotu, která určuje, která třída libovolný záznam patří.

Představte si třeba `Persons` tabulku, která obsahuje všechny uživatele náhradník společnosti. Někteří lidé jsou zaměstnanci a někteří lidé jsou správci. `Persons` Tabulka obsahuje sloupec s názvem `EmployeeType` , který má hodnotu 1 pro manažery a hodnota 2 pro zaměstnance; to je sloupec diskriminátoru. V tomto scénáři můžete vytvořit podtřídu zaměstnanců a naplnit třída se pouze záznamy, které mají `EmployeeType` hodnotu 2. Můžete také odebrat sloupce, které se nevztahují z každé třídy.

Vytvoření objektu modelu, který používá dědičnosti (a odpovídá relační data) může být trochu matoucí. Následující postup popisuje kroky potřebné ke konfiguraci dědičnosti s **O/R Designer**. Podle obecných kroků bez ohledu na existující tabulky a sloupce může být obtížné, proto je k dispozici návod, který používá data. Podrobné pokyny krok za krokem konfigurace dědičnosti pomocí **O/R Designer**, naleznete v tématu [názorný postup: Vytvoření LINQ na třídy SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md).

## <a name="to-create-inherited-data-classes"></a>Chcete-li vytvořit zděděné datových tříd

1.  Otevřít **O/R Designer** tak, že přidáte **třídy LINQ to SQL** položky do existující jazyka Visual Basic nebo C# projektu.

2.  Přetáhněte tabulku, kterou chcete použít jako základní třídy na **O/R Designer**.

3.  Přetáhněte kopii tabulky do druhé **O/R Designer** a přejmenujte jej. Jedná se o odvozené třídy nebo podtřídy.

4.  Klikněte na tlačítko **dědičnosti** v **Návrhář relací objektů** karty **nástrojů**a potom klikněte na podtřídu (tabulky, které jste přejmenovali) a připojte ho k základní třídy.

    > [!NOTE]
    >  Klikněte na tlačítko **dědičnosti** položky v **nástrojů** a uvolněte tlačítko myši, klikněte na druhé kopie třídy, kterou jste vytvořili v kroku 3 a pak klikněte na první třídy, kterou jste vytvořili v kroku 2. Šipka na čáru dědičnosti odkazuje na první třídy.

5.  V každé třídě odstraňte všechny vlastnosti objektu, které nechcete zobrazit a které nejsou používány pro přidružení. Pokud se pokusíte odstranit vlastnosti objektu použité pro přidružení zobrazí chybová zpráva: [Vlastnost \<název vlastnosti > nejde odstranit, protože se účastní asociace \<název přidružení >](../data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name.md).

    > [!NOTE]
    >  Protože odvozené třídy dědí vlastnosti definované v její základní třídě, stejné sloupce se nedá definovat v každé třídě. (Sloupce jsou implementovány jako vlastnosti). Vytvoření sloupce v odvozené třídě můžete povolit tak, že nastavíte modifikátor dědičnosti na vlastnost v základní třídě. Další informace najdete v tématu [základní informace o dědičnosti (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics).

6.  Vybrat čáru dědičnosti v **O/R Designer**.

7.  V **vlastnosti** okno, nastaveno **vlastnost diskriminátoru** název sloupce, který odlišuje záznamy ve třídách.

8.  Nastavte **hodnota diskriminátoru odvozené třídy** k hodnotě v databázi, která se označí jako zděděný typ záznamu. (To je hodnota, která jsou uložena v sloupec diskriminátoru a slouží k určení zděděné třídy.)

9. Nastavte **hodnota diskriminátoru základní třídy** vlastnost na hodnotu, která se označí jako základní typ záznamu. (To je hodnota, která jsou uložena v sloupec diskriminátoru a slouží k určení základní třídy).

10. Volitelně můžete také nastavit **výchozí dědičnost** vlastnosti k určení typu v hierarchii dědičnosti, který se používá při načítání řádků, které neodpovídají žádné definované kód dědičnosti. Jinými slovy, pokud má záznam hodnotu v jeho sloupec diskriminátoru, která se neshoduje s hodnotu buď **hodnota diskriminátoru odvozené třídy** nebo **hodnota diskriminátoru základní třídy** vlastnosti, záznam načte typ určený jako **výchozí dědičnost**.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytvoření LINQ na třídy SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Návod: Vytvoření LINQ na třídy SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
- [Základní informace o dědičnosti (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)
- [Dědičnost](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)