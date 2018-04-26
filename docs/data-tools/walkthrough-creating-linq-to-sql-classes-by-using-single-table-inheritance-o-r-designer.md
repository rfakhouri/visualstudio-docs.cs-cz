---
title: 'Návod: Vytvoření třídy LINQ to SQL s použitím dědičnosti jedné tabulky (Návrhář O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 33da9618fa469961edddb685c4cc5b00ccd71a73
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>Návod: Vytvoření třídy LINQ to SQL s použitím dědičnosti jedné tabulky (Návrhář relací objektů)
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) podporuje jedno tabulková dědičnost obvykle je implementované v relačním systémech. Tento názorný postup jejich rozšířením obecné kroky uvedené v [postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) tématu a poskytuje některé reálná data za účelem ukázky použití dědičnosti v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

 Během tohoto návodu budete provádět následující úlohy:

-   Vytvořit tabulku databáze a přidejte do ní data.

-   Vytvořte aplikaci Windows Forms.

-   Přidat [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] souboru do projektu.

-   Vytvořte nové třídy entity.

-   Nakonfigurujte použití dědičnosti třídy entity.

-   Dotaz na zděděné třídy.

-   Zobrazení dat ve formuláři Windows.

## <a name="create-a-table-to-inherit-from"></a>Vytvořte tabulku pro dědí
 Pokud chcete zjistit, jak funguje dědičnosti, bude vytvoření malé tabulky osoba, použít jako základní třída a pak vytvořte objekt zaměstnanec, který dědí z něj.

#### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>K vytvoření základní tabulky k předvedení dědičnosti

1.  V **Průzkumníka serveru**/**Průzkumník databáze**, klikněte pravým tlačítkem myši **tabulky** uzel a klikněte na tlačítko **přidat novou tabulku**.

    > [!NOTE]
    >  Můžete použít databázi Northwind nebo můžete přidat tabulku pro všechny ostatní databáze.

2.  V návrháře tabulky přidejte následující sloupce do tabulky:

    |Název sloupce|Datový typ|Povolit hodnoty Null|
    |-----------------|---------------|-----------------|
    |**ID**|**int**|**False**|
    |**Typ**|**int**|**Hodnota TRUE**|
    |**FirstName**|**Nvarchar(200)**|**False**|
    |**LastName**|**Nvarchar(200)**|**False**|
    |**Správce**|**int**|**Hodnota TRUE**|

3.  Sloupec ID nastavte jako primární klíč.

4.  Uložte tabulku a pojmenujte ji **osoba**.

## <a name="add-data-to-the-table"></a>Přidání dat do tabulky
 Aby mohli ověřit, zda je správně nakonfigurována dědičnosti, musí v tabulce některá data pro každou třídu v jedné tabulce dědičnosti.

#### <a name="to-add-data-to-the-table"></a>Chcete-li přidat data do tabulky

1.  Otevřete v tabulce v zobrazení. (Klikněte pravým tlačítkem myši **osoba** tabulky v **Průzkumníka serveru**/**Průzkumník databáze** a klikněte na tlačítko **zobrazit Data tabulky**.)

2.  Zkopírujte následující data do tabulky. (Můžete ho zkopírujte a vložte jej do tabulky celý řádek, vyberte v podokně výsledků.)

    ||||||
    |-|-|-|-|-|
    |**ID**|**Typ**|**FirstName**|**LastName**|**Správce**|
    |**1**|**1**|**Dana**|**Wallace**|**HODNOTU NULL**|
    |**2**|**1**|**Carlosi**|**Grilo**|**HODNOTU NULL**|
    |**3**|**1**|**Yael**|**Peled**|**HODNOTU NULL**|
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|
    |**5**|**2**|**Andreas**|**Hauser**|**1**|
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|
    |**9**|**2**|**Tai**|**Jí**|**2**|
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|
    |**11**|**2**|**Robert**|**Martin**|**3**|
    |**12**|**2**|**Ken**|**Kwok**|**3**|

## <a name="create-a-new-project"></a>Vytvoření nového projektu
 Teď, když jste vytvořili v tabulce, vytvořte nový projekt k předvedení konfigurace dědičnosti.

#### <a name="to-create-the-new-windows-forms-application"></a>Chcete-li vytvořit novou aplikaci Windows Forms

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

4. Název projektu **InheritanceWalkthrough**a potom zvolte **OK**.

     **InheritanceWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.

## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>Přidat LINQ to SQL třídy souboru do projektu

#### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>Chcete-li do projektu přidejte LINQ to SQL souboru

1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.

2.  Klikněte **třídy LINQ to SQL** šablony a pak klikněte na tlačítko **přidat**.

     Soubor DBML se přidá do projektu a [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] otevře.

## <a name="create-the-inheritance-by-using-the-or-designer"></a>Vytvořit vztah dědičnosti pomocí Návrhář relací objektů
 Konfigurace dědičnosti přetažením **dědičnosti** objektu z **sada nástrojů** na návrhovou plochu.

#### <a name="to-create-the-inheritance"></a>Chcete-li vytvořit vztah dědičnosti

1.  V **Průzkumníka serveru**/**Průzkumník databáze**, přejděte na **osoba** tabulky, který jste vytvořili dříve.

2.  Přetáhněte **osoba** do tabulky [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] návrhovou plochu.

3.  Přetáhněte druhý **osoba** do tabulky [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] a změňte jeho název **zaměstnanec**.

4.  Odstranit **Manager** vlastnost z **osoba** objektu.

5.  Odstranit **typ**, **ID**, **FirstName**, a **LastName** vlastnosti z **zaměstnanec** objektu. (Jinými slovy, odstranit všechny vlastnosti s výjimkou **Manager**.)

6.  Z **Návrhář relací objektů** kartě **sada nástrojů**, vytvořit **dědičnosti** mezi **osoba** a  **Zaměstnanec** objekty. Chcete-li to provést, klikněte na tlačítko **dědičnosti** položky v **sada nástrojů** a uvolněním tlačítka myši. Klikněte na tlačítko **zaměstnanec** objekt a potom **osoba** objekt v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Bude odkazovat na šipku v řádku dědičnosti **osoba** objektu.

7.  Klikněte **dědičnosti** řádku na návrhovou plochu.

8.  Nastavte **diskriminátoru vlastnost** vlastnost **typu**.

9. Nastavte **odvozené třídy diskriminátoru hodnotu** vlastnost **2**.

10. Nastavte **hodnota diskriminátoru základní třídy** vlastnost **1**.

11. Nastavte **dědičnosti výchozí** vlastnost **osoba**.

12. Sestavte projekt.

## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>Dotaz na zděděné třídy a zobrazení dat ve formuláři
 Nyní přidáte nějaký kód do formuláře, který se dotazuje na určité třídy v objektovém modelu.

#### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>K vytvoření dotazu LINQ a zobrazit výsledky na formuláři

1.  Přetáhněte **ListBox** na Form1.

2.  Klikněte dvakrát na formuláři vytvořte `Form1_Load` obslužné rutiny události.

3.  Přidejte následující kód, který `Form1_Load` obslužné rutiny události:

    ```vb
    Dim dc As New DataClasses1DataContext
    Dim results = From emp In dc.Persons _
        Where TypeOf emp Is Employee _
        Select emp

    For Each Emp As Employee In results
        ListBox1.Items.Add(Emp.LastName)
    Next
    ```

    ```csharp
    NorthwindDataContext dc = new DataClasses1DataContext();
    var results = from emp in dc.Persons
                  where emp is Employee
                  select emp;

    foreach(Employee Emp in results)
    {
        listBox1.Items.Add(Emp.LastName)
    }
    ```

## <a name="test-the-application"></a>Testování aplikace
 Spusťte aplikaci a ověřte, zda jsou záznamy zobrazené v seznamu všechny zaměstnance (záznamy, které mají hodnotu 2 v jejich sloupce typu).

#### <a name="to-test-the-application"></a>Testování aplikace

1.  Stiskněte klávesu F5.

2.  Ověřte, zda jsou zobrazeny pouze záznamy, které mají hodnotu 2 v jejich sloupec typu.

3.  Zavřete formulář. (Na **ladění** nabídky, klikněte na tlačítko **Zastavte ladění**.)

## <a name="see-also"></a>Viz také

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytváření třídy LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Postupy: Generování objektového modelu v jazyce Visual Basic nebo C#](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)