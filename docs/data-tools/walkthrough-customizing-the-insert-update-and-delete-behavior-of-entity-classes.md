---
title: "Návod: Přizpůsobení vložit, aktualizovat a odstraňovat chování tříd entit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 03ff1146-706e-4780-91cb-56a83df63eea
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: e4edcc21986ae0fd033228971697057932e63670
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes"></a>Návod: Přizpůsobení vložit, aktualizovat a odstraňovat chování tříd entit
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) poskytuje návrhové ploše k vytváření a úpravy [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy (třídy entity), které jsou založeny na objekty v databázi. Pomocí [technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index), můžete použít technologie LINQ pro přístup k databázím SQL. Další informace najdete v tématu [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/).  
  
Ve výchozím nastavení, je poskytována logiku pro provádění aktualizací [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] modulu runtime. Modul runtime vytvoří výchozí příkazy Insert, Update a Delete na základě schématu tabulky (definice sloupců a informace o primárním klíči). Pokud nechcete použít výchozí chování, můžete konfigurovat chování aktualizací a určit konkrétní uložené procedury pro provádění nezbytné vložení, aktualizace a odstranění potřebné pro práci s daty v databázi. Můžete také k tomu generování výchozí chování není, například pokud vaše třídy entity mapování na zobrazení. Kromě toho můžete přepsat výchozí chování aktualizace, pokud databáze vyžaduje přístup k tabulce prostřednictvím uložených procedur. Další informace najdete v tématu [přizpůsobení Operations podle pomocí uložené procedury](/dotnet/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures).  
  
> [!NOTE]
>  Tento postup vyžaduje dostupnost **InsertCustomer**, **UpdateCustomer**, a **DeleteCustomer** uložené procedury pro databázi Northwind.  
  
Tento názorný postup obsahuje kroky, které je třeba provést při přepsat výchozí nastavení LINQ SQL modul runtime chování pro ukládání dat zpět do databáze pomocí uložené procedury.  
  
Během tohoto návodu se dozvíte, jak provádět následující úlohy:  
  
-   Vytvořte novou aplikaci Windows Forms a přidejte [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] souboru k němu.  
  
-   Vytvořte třídu entity, který je namapovaný na tabulku zákazníků Northwind.  
  
-   Vytvořte zdroj dat objektu, který odkazuje na LINQ to SQL zákazníka třídy.  
  
-   Vytvoření formuláře Windows, který obsahuje <xref:System.Windows.Forms.DataGridView> , je vázán k třídě zákazníka.  
  
-   Implementace uložit funkce pro daný formulář.  
  
-   Vytvoření <xref:System.Data.Linq.DataContext> metody přidáním uložené procedury k [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
-   Konfigurovat třídu zákazníka pomocí uložené procedury provést vložení, aktualizace a odstranění.  
  
## <a name="prerequisites"></a>Požadavky  
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  
  
1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.  
  
2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
## <a name="creating-an-application-and-adding-linq-to-sql-classes"></a>Vytváření aplikací a přidání LINQ do třídy SQL  
Vzhledem k tomu, že budete pracovat s [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy a zobrazování dat ve formuláři Windows vytvořit novou aplikaci Windows Forms a přidejte do souboru SQL třídy LINQ.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-a-new-windows-forms-application-project-that-contains-linq-to-sql-classes"></a>Chcete-li vytvořit nový projekt aplikace Windows Forms, který obsahuje LINQ na třídy SQL  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **UpdatingWithSProcsWalkthrough**a potom zvolte **OK**. 
  
     **UpdatingWithSProcsWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.  
  
4.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
5.  Klikněte **třídy LINQ to SQL** šablonu a zadejte **Northwind.dbml** v **název** pole.  
  
6.  Klikněte na tlačítko **přidat**.  
  
     Prázdný technologie LINQ to SQL třídy souboru (Northwind.dbml) se přidá do projektu a [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] otevře.  
  
## <a name="creating-the-customer-entity-class-and-object-data-source"></a>Vytvoření třídy entita zákazník a zdroj dat objektu  
 Vytvoření [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy, které jsou namapované na tabulkách databáze tak, že přetáhnete tabulky z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Výsledkem je LINQ SQL tříd entit, které jsou mapovány na tabulky v databázi. Po vytvoření tříd entit, můžete použít jako zdroje dat objektu stejně jako jiné třídy, které mají veřejné vlastnosti.  
  
#### <a name="to-create-a-customer-entity-class-and-configure-a-data-source-with-it"></a>Vytvořte třídu entity zákazníka a nakonfigurujte zdroj dat s ním  
  
1.  V **Průzkumníka serveru**/**Průzkumník databáze**, najít tabulku zákazníků v této verzi systému SQL Server ukázková databáze Northwind. 
  
2.  Přetáhněte **zákazníci** uzlu z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] prostor.  
  
     Třídu entity s názvem **zákazníka** je vytvořena. Obsahuje vlastnosti, které odpovídají na sloupce v tabulce Zákazníci. Název třídy entita **zákazníka** (není **zákazníků**) protože reprezentuje jednoho zákazníka z tabulky zákazníků.  
  
    > [!NOTE]
    >  Toto chování přejmenování se nazývá *pluralizační*. Ho můžete zapnout nebo vypnout [dialogové okno Možnosti](../ide/reference/options-dialog-box-visual-studio.md). Další informace najdete v tématu [postupy: vypnutí pluralizační a zapnutí (Návrhář relací objektů)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md).  
  
3.  Na **sestavení** nabídky, klikněte na tlačítko **sestavení UpdatingwithSProcsWalkthrough** a tím projekt sestavit.  
  
4.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.  
  
5.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.  
  
6.  Klikněte na tlačítko **objekt** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.  
  
7.  Rozbalte položku **UpdatingwithSProcsWalkthrough** uzlu a najděte a vyberte **zákazníka** třídy.  
  
    > [!NOTE]
    >  Pokud **zákazníka** třída není k dispozici, ukončete průvodce, sestavte projekt a opakujte akci.  
8.  Klikněte na tlačítko **Dokončit** vytvoření zdroje dat a přidat **zákazníka** třídu entity k **zdroje dat** okno.  
  
## <a name="creating-a-datagridview-to-display-the-customer-data-on-a-windows-form"></a>Vytváření DataGridView k zobrazení dat zákazníka ve formuláři Windows  
 Vytváření ovládacích prvků, které jsou vázány na tříd entit, tak, že přetáhnete [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] položek ze zdroje dat **zdroje dat** okno na formuláři Windows.  
  
#### <a name="to-add-controls-that-are-bound-to-the-entity-classes"></a>K přidávání ovládacích prvků, které jsou vázány na tříd entit  
  
1.  Otevřete Form1 v zobrazení návrhu.  
  
2.  Z **zdroje dat** okno, přetáhněte **zákazníka** uzlu na Form1.  
  
    > [!NOTE]
    >  K zobrazení **zdroje dat** okně klikněte na tlačítko **zobrazit zdroje dat** na **Data** nabídky.  
  
3.  Otevřete v editoru kódu Form1.  
  
4.  Přidejte následující kód do formuláře, globální formuláře, mimo určení způsobu, ale uvnitř Form1 třídy:  
  
    ```vb  
    Private NorthwindDataContext1 As New NorthwindDataContext  
    ```  
  
    ```csharp  
    private NorthwindDataContext northwindDataContext1  
        = new NorthwindDataContext();    
    ```  
  
5.  Vytvoření obslužné rutiny událostí `Form_Load` událostí a přidejte následující kód do obslužné rutiny:  
  
    ```vb  
    CustomerBindingSource.DataSource = NorthwindDataContext1.Customers  
    ```  
  
    ```csharp  
    customerBindingSource.DataSource  
        = northwindDataContext1.Customers;    
    ```  
  
## <a name="implementing-save-functionality"></a>Implementace funkce uložení  
 Ve výchozím nastavení, uložení tlačítko není povoleno a uložte funkce není implementována. Navíc kód není automaticky přidáno uložte změněná data do databáze při vytvoření ovládací prvky vázané na data pro zdroje dat objektu. Tato část vysvětluje, jak povolit uložení tlačítko a implementovat funkce pro uložení [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] objekty.  
  
#### <a name="to-implement-save-functionality"></a>K implementaci uložit funkce  
  
1.  Otevřete Form1 v zobrazení návrhu.  
  
2.  Vyberte uložení tlačítko **CustomerBindingNavigator** (tlačítko s ikonou disketovou jednotku).  
  
3.  V **vlastnosti** nastavte **povoleno** vlastnost **True**.  
  
4.  Poklikejte na soubor uložit tlačítko pro vytvoření obslužné rutiny události a přepněte do editoru kódu.  
  
5.  Přidejte následující kód do uložení obslužnou rutinu události:  
  
    ```vb  
    NorthwindDataContext1.SubmitChanges()  
    ```  
  
    ```csharp  
    northwindDataContext1.SubmitChanges();  
    ```  
  
## <a name="overriding-the-default-behavior-for-performing-updates-inserts-updates-and-deletes"></a>Přepsání výchozího nastavení pro provádění aktualizací (vložení, aktualizace a odstranění)  
  
#### <a name="to-override-the-default-update-behavior"></a>Chcete-li přepsat výchozí chování aktualizace  
  
1.  Otevřete LINQ to SQL souboru v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Dvakrát klikněte **Northwind.dbml** souboru v **Průzkumníku řešení**.)  
  
2.  V **Průzkumníka serveru**/**Průzkumník databáze**, rozbalte položku databáze Northwind **uložené procedury** uzlu a najděte  **InsertCustomers**, **UpdateCustomers**, a **DeleteCustomers** uložené procedury.  
  
3.  Přetáhněte všechny tři uložené procedury na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
     Uložené procedury jsou přidány do podokna metody jako <xref:System.Data.Linq.DataContext> metody. Další informace najdete v tématu [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).  
  
4.  Vyberte **zákazníka** třídy entita v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
5.  V **vlastnosti** vyberte **vložit** vlastnost.  
  
6.  Klikněte na tlačítko se třemi tečkami (...) vedle **modulu Runtime použijte** otevřete **nakonfigurovat chování** dialogové okno.  
  
7.  Vyberte **přizpůsobit**.  
  
8.  Vyberte **InsertCustomers** metoda v **přizpůsobit** seznamu.  
  
9. Klikněte na tlačítko **použít** uložit konfiguraci pro vybranou třídu a chování.  
  
    > [!NOTE]
    >  Můžete pokračovat, dokud po kliknutí na tlačítko Konfigurovat chování pro každou kombinaci třída/chování **použít** po každé změně. Pokud změníte třídu nebo chování před kliknutím na **použít**, dialogové okno upozornění poskytuje, zobrazí se možnost použít všechny změny.  
  
10. Vyberte **aktualizace** v **chování** seznamu.  
  
11. Vyberte **přizpůsobit**.  
  
12. Vyberte **UpdateCustomers** metoda v **přizpůsobit** seznamu.  
  
     Zkontrolujte seznam **metoda argumenty** a **vlastnosti třídy** a Všimněte si, že existují dvě **metoda argumenty** a dvě **vlastnosti třídy**pro některé sloupce v tabulce. To usnadňuje sledování změn a vytváření příkazů, které kontrolovat porušení souběžnosti.  
  
13. Mapy **Original_CustomerID** metoda argument **CustomerID (původní)** vlastnost třídy.  
  
    > [!NOTE]
    >  Ve výchozím nastavení bude metoda argumenty mapovat na vlastnosti třídy, když se názvy shodují s. Pokud se názvy vlastností se změní a už neodpovídá mezi tabulkou a třídu entity, můžete chtít, vyberte vlastnost ekvivalentní třídy mapovat Pokud Návrhář relací objektů nemůže určit správné mapování. Kromě toho, pokud metoda argumenty nemají vlastnosti platnou třídu pro mapování na, můžete nastavit **vlastnosti třídy** hodnotu **(None)**.  
  
14. Klikněte na tlačítko **použít** uložit konfiguraci pro vybranou třídu a chování.  
  
15. Vyberte **odstranit** v **chování** seznamu.  
  
16. Vyberte **přizpůsobit**.  
  
17. Vyberte **DeleteCustomers** metoda v **přizpůsobit** seznamu.  
  
18. Mapy **Original_CustomerID** metoda argument **CustomerID (původní)** vlastnost třídy.  
  
19. Click **OK**.  
  
> [!NOTE]
>  Ačkoli to není v tomto návodu konkrétní problém, je to, že [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] zpracovává generované hodnoty automaticky identity (automatického přírůstku), rowguidcol (generované GUID) a sloupce časového razítka při vložení a aktualizace. Generované hodnoty v jiné typy sloupců povede neočekávaně hodnotu null. K návratu hodnot generované databáze, měli byste ručně nastavit <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> k `true` a <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> na jednu z následujících: <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync>, nebo <xref:System.Data.Linq.Mapping.AutoSync>.  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Spusťte aplikaci znovu a ověřte, zda **UpdateCustomers** uložené procedury správně aktualizuje zákazníka záznam v databázi.  
  
#### <a name="to-test-the-application"></a>Testování aplikace  
  
1.  Stiskněte klávesu F5.  
  
2.  Upravte záznamu v mřížce k testování chování aktualizací.  
  
3.  Přidejte nový záznam pro testování chování Insert.  
  
4.  Klikněte na tlačítko Uložit uložte změny zpět do databáze.  
  
5.  Zavřete formulář.  
  
6.  Stisknutím klávesy F5 a ověřte, že aktualizovaný záznam a nově vloženého záznamu trvalé.  
  
7.  Odstranění nový záznam, kterou jste vytvořili v kroku 3 pro testování chování odstranit.  
  
8.  Klikněte na toto tlačítko a odeslat provedené změny a odebrat odstraněné záznam z databáze  
  
9. Zavřete formulář.  
  
10. Stisknutím klávesy F5 a ověřte, že odstraněného záznamu byla odebrána z databáze.  
  
    > [!NOTE]
    >  Pokud vaše aplikace používá SQL Server Express Edition, v závislosti na hodnotě **kopírovat do výstupního adresáře** vlastnost souboru databáze, změny se při stisknutí klávesy F5 v kroku 10. 
  
## <a name="next-steps"></a>Další kroky  
V závislosti na požadavcích vaší aplikace, existuje několik kroků, které můžete provést po vytvoření [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] tříd entit. Některé vylepšení, které provedete může tato aplikace patří:  
  
-   Implementujte souběžnost kontroly během aktualizace. Informace najdete v tématu [optimistickou metodu souběžného: Přehled](/dotnet/framework/data/adonet/sql/linq/optimistic-concurrency-overview).  
  
-   Přidání dotazů LINQ do filtru data. Informace najdete v tématu [Úvod do dotazů LINQ (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).  
  
## <a name="see-also"></a>Viz také
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)     
[DataContext metody](../data-tools/datacontext-methods-o-r-designer.md)   
[Postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)  
[Dotazy LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/linq-to-sql-queries)  
 