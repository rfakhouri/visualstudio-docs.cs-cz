---
title: Vyhledávací tabulky v datové vazby – ovládací prvky Windows Forms | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- LookupBindingPropertiesAttribute class, examples
- user controls [Visual Basic], creating
ms.assetid: c48b4d75-ccfc-4950-8b14-ff8adbfe4208
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 8ec105b59f922ae56e9a07c310612f66bb3ef0a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-windows-forms-user-control-that-supports-lookup-data-binding"></a>Vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje vyhledávání datová vazba
Při zobrazování dat ve Windows Forms, můžete zvolit existující ovládacích prvků z **sada nástrojů**, nebo můžete vytvořit vlastní ovládací prvky, pokud vaše aplikace vyžaduje funkce není k dispozici ve standardní ovládací prvky. Tento návod ukazuje postup vytvoření ovládacího prvku, který implementuje <xref:System.ComponentModel.LookupBindingPropertiesAttribute>. Určuje, které implementují <xref:System.ComponentModel.LookupBindingPropertiesAttribute> může obsahovat tři vlastnosti, které mohou být vázány na data. Tyto prvky jsou podobné <xref:System.Windows.Forms.ComboBox>.  
  
 Další informace o vytváření řízení najdete v tématu [vývoj ovládacích prvků Windows Forms v době návrhu](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).  
  
 Při vytváření ovládacích prvků pro použití v scénáře datových vazeb potřebujete implementovat jednu z následujících atributů datové vazby:  
  
|Používání atributu datová vazba|  
|-----------------------------------|  
|Implementace <xref:System.ComponentModel.DefaultBindingPropertyAttribute> na jednoduché ovládací prvky, jako <xref:System.Windows.Forms.TextBox>, který jeden sloupec (nebo vlastnost) dat zobrazit. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje jednoduchou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|  
|Implementace <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> na ovládací prvky, jako <xref:System.Windows.Forms.DataGridView>, který zobrazí seznamy (nebo tabulky) data. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje rozšířené datové vazby](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|  
|Implementace <xref:System.ComponentModel.LookupBindingPropertiesAttribute> na ovládací prvky, jako je <xref:System.Windows.Forms.ComboBox>, které zobrazí seznamy (nebo tabulky) data, ale také muset jeden sloupec nebo vlastnost k dispozici. (Tento proces je popsaný v této stránce návod.)|  
  
 Tento návod vytvoří ovládacího prvku vyhledávání, která se váže k datům ze dvou tabulek. Tento příklad používá `Customers` a `Orders` tabulky z ukázková databáze Northwind. Ovládací prvek vyhledávání bude vázán k `CustomerID` pole z `Orders` tabulky. Tato hodnota se bude používat pro vyhledání `CompanyName` z `Customers` tabulky.  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Vytvořte novou **formulářové aplikace Windows**.  
  
-   Přidejte nový **uživatelský ovládací prvek** do projektu.  
  
-   Vizuální návrh uživatelského ovládacího prvku.  
  
-   Implementace `LookupBindingProperty` atribut.  
  
-   Vytvořit datovou sadu s **konfigurace zdroje dat** průvodce.  
  
-   Nastavit **CustomerID** sloupec **objednávky** tabulky v **zdroje dat** okno používat nový ovládací prvek.  
  
-   Vytvořte formulář k zobrazení dat v ovládacím prvku nové.  
  
## <a name="prerequisites"></a>Požadavky

Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  

1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.

2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
## <a name="create-a-windows-forms-application"></a>Vytvoření aplikace Windows Forms  
 Prvním krokem je vytvoření **formulářové aplikace Windows**.  
  
#### <a name="to-create-the-new-windows-project"></a>Vytvoření nového projektu Windows  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **LookupControlWalkthrough**a potom zvolte **OK**. 
  
     **LookupControlWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.  
  
## <a name="add-a-user-control-to-the-project"></a>Do projektu přidejte uživatelský ovládací prvek  
 Tento návod vytvoří ovládacího prvku vyhledávání z **uživatelský ovládací prvek**, proto přidat **uživatelský ovládací prvek** položkou **LookupControlWalkthrough** projektu.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>Chcete-li přidat uživatelský ovládací prvek do projektu  
  
1.  Z **projektu** nabídce vyberte možnost **přidat uživatelský ovládací prvek**.  
  
2.  Typ `LookupBox` v **název** oblasti a pak klikněte na tlačítko **přidat**.  
  
     **LookupBox** ovládací prvek je přidán do **Průzkumníku**a otevře v návrháři.  
  
## <a name="design-the-lookupbox-control"></a>Návrh LookupBox ovládací prvek  
  
#### <a name="to-design-the-lookupbox-control"></a>Při návrhu LookupBox ovládací prvek  
  
-   Přetáhněte <xref:System.Windows.Forms.ComboBox> z **sada nástrojů** na návrhovou plochu uživatelského ovládacího prvku.  
  
## <a name="add-the-required-data-binding-attribute"></a>Přidejte požadovaný atribut datová vazba  
 Pro vyhledávání určuje, že podpora datová vazba, můžete implementovat <xref:System.ComponentModel.LookupBindingPropertiesAttribute>.  
  
#### <a name="to-implement-the-lookupbindingproperties-attribute"></a>K implementaci atribut LookupBindingProperties  
  
1.  Přepínač **LookupBox** řízení zobrazení kódu. (Na **zobrazení** nabídce zvolte **kód**.)  
  
2.  Nahraďte kód v `LookupBox` následujícím kódem:  
  
     [!code-vb[VbRaddataDisplaying#5](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.vb)]
     [!code-csharp[VbRaddataDisplaying#5](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.cs)]  
  
3.  Z **sestavení** nabídce zvolte **sestavit řešení**.  
  
## <a name="create-a-data-source-from-your-database"></a>Vytvoření zdroje dat z databáze  
Tento krok vytvoří zdroje dat pomocí **konfigurace zdroje dat**průvodce, na základě `Customers` a `Orders` tabulky v ukázkové databázi Northwind.  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.  
  
2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **konfigurace zdroje dat** průvodce.  
  
3.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.  
  
4.  Na **zvolit datové připojení** proveďte jednu z následujících akcí:  
  
    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.  
  
    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.  
  
5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data, a pak klikněte na **Další**.  
  
6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.  
  
7.  Na **zvolte databázové objekty** rozbalte **tabulky** uzlu.  
  
8.  Vyberte `Customers` a `Orders` tabulky a pak klikněte na tlačítko **Dokončit**.  
  
     **NorthwindDataSet** se přidá do projektu a `Customers` a `Orders` tabulky se zobrazí v **zdroje dat** okno.  
  
## <a name="set-the-customerid-column-of-the-orders-table-to-use-the-lookupbox-control"></a>Nastavit sloupce CustomerID tabulce objednávky použití ovládacího prvku LookupBox  
 V rámci **zdroje dat** okně můžete nastavit ovládací prvek, který má být vytvořen před přetáhnete položky do formuláře.  
  
#### <a name="to-set-the-customerid-column-to-bind-to-the-lookupbox-control"></a>Chcete-li nastavit sloupce CustomerID k vytvoření vazby na ovládací prvek LookupBox  
  
1.  Otevřete **Form1** v návrháři.  
  
2.  Rozbalte **zákazníci** uzel v **zdroje dat** okno.  
  
3.  Rozbalte **objednávky** uzlu (v **zákazníci** uzlu níže **Fax** sloupce).  
  
4.  Klikněte na šipku rozevíracího seznamu **objednávky** uzel a zvolte **podrobnosti** ze seznamu řízení.  
  
5.  Klikněte na šipku rozevíracího seznamu **CustomerID** sloupce (v **objednávky** uzlu) a zvolte **přizpůsobit**.  
  
6.  Vyberte **LookupBox** ze seznamu **související ovládací prvky** v **možnosti přizpůsobení uživatelského rozhraní dat** dialogové okno.  
  
7.  Click **OK**.  
  
8.  Klikněte na šipku rozevíracího seznamu **CustomerID** sloupce a vyberte **LookupBox**.  
  
## <a name="add-controls-to-the-form"></a>Přidání ovládacích prvků formuláře  
 Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do **Form1**.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Chcete-li vytvořit ovládací prvky vázané na data ve formuláři Windows  
  
-   Přetáhněte **objednávky** uzlu z **zdroje dat** window do formuláře systému Windows a ověřte, že **LookupBox** řízení se používá k zobrazení dat v `CustomerID` sloupec.  
  
## <a name="bind-the-control-to-look-up-companyname-from-the-customers-table"></a>Vytvoření vazby ovládacího prvku k vyhledání NázevSpolečnosti z tabulky Zákazníci  
  
#### <a name="to-setup-the-lookup-bindings"></a>K nastavení vyhledávání vazby  
  
-   Vyberte hlavní **zákazníci** uzel v **zdroje dat** okna a přetáhněte ji do se seznamem se pole v **CustomerIDLookupBox** na **Form1** .  
  
     Toto nastaví datové vazby k zobrazení `CompanyName` z `Customers` tabulce, při zachování `CustomerID` z hodnoty `Orders` tabulky.  
  
## <a name="running-the-application"></a>Spuštění aplikace  
  
#### <a name="to-run-the-application"></a>Ke spuštění aplikace  
  
-   Stisknutím klávesy F5 spusťte aplikaci.  
  
-   Procházet některé záznamy a ověřte, zda `CompanyName` se zobrazí v `LookupBox` ovládacího prvku.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
