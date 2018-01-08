---
title: "Vytvoření uživatelského ovládacího prvku Windows Forms pomocí datové vazby | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- data binding, complex
- user controls [Visual Studio], complex data binding
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c5e59b34a1093b90320bfdd05989913e72600a8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="create-a-windows-forms-user-control-that-supports-complex-data-binding"></a>Vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje rozšířené datové vazby

Při zobrazení dat ve formulářích v aplikacích Windows, můžete zvolit existující ovládacích prvků z **sada nástrojů**, nebo můžete vytvořit vlastní ovládací prvky, pokud vaše aplikace vyžaduje funkce, která není k dispozici v standardní ovládací prvky. Tento návod ukazuje postup vytvoření ovládacího prvku, který implementuje <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>. Určuje, které implementují <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> obsahovat `DataSource` a `DataMember` vlastnost, která mohou být vázány na data. Tyto prvky jsou podobné <xref:System.Windows.Forms.DataGridView> nebo <xref:System.Windows.Forms.ListBox>.

Další informace o vytváření řízení najdete v tématu [vývoj ovládacích prvků Windows Forms v době návrhu](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).

Při vytváření ovládacích prvků pro použití v scénáře datových vazeb potřebujete implementovat jednu z následujících atributů datové vazby:

|Používání atributu datová vazba|
|-----------------------------------|
|Implementace <xref:System.ComponentModel.DefaultBindingPropertyAttribute> na jednoduché ovládací prvky, jako <xref:System.Windows.Forms.TextBox>, který jeden sloupec (nebo vlastnost) dat zobrazit. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje jednoduchou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|
|Implementace <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> na ovládací prvky, jako <xref:System.Windows.Forms.DataGridView>, který zobrazí seznamy (nebo tabulky) data. (Tento proces je popsaný v této stránce návod.)|
|Implementace <xref:System.ComponentModel.LookupBindingPropertiesAttribute> na ovládací prvky, jako je <xref:System.Windows.Forms.ComboBox>, které zobrazí seznamy (nebo tabulky) data, ale také muset jeden sloupec nebo vlastnost k dispozici. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje datovou vazbu vyhledání](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|

 Tento návod vytvoří komplexní ovládací prvek, který zobrazuje řádky dat z tabulky. Tento příklad používá `Customers` tabulku z ukázková databáze Northwind. Komplexní uživatelského ovládacího prvku se zobrazí tabulku zákazníků v <xref:System.Windows.Forms.DataGridView> v vlastního ovládacího prvku.

Během tohoto návodu se dozvíte, jak:

- Vytvořte novou **formulářové aplikace Windows**.

- Přidejte nový **uživatelský ovládací prvek** do projektu.

- Vizuální návrh uživatelského ovládacího prvku.

- Implementace `ComplexBindingProperty` atribut.

- Vytvořit datovou sadu s [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png).

- Nastavte **zákazníci** tabulky v [okno zdroje dat](add-new-data-sources.md) používat nový komplexní řízení.

- Přidat nový ovládací prvek přetažením z **okno zdroje dat** na **Form1**.

## <a name="prerequisites"></a>Požadavky

Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.

1. Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.

1. Ukázková databáze Northwind nainstalujte pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .

       Otevře se okno editoru dotazů.

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.

## <a name="create-a-windows-forms-application"></a>Vytvoření aplikace Windows Forms

 Prvním krokem je vytvoření **formulářové aplikace Windows**.

### <a name="to-create-the-new-windows-project"></a>Vytvoření nového projektu Windows

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .

1. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.

1. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

1. Název projektu **ComplexControlWalkthrough**a potom zvolte **OK**.

    **ComplexControlWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.

## <a name="add-a-user-control-to-the-project"></a>Do projektu přidejte uživatelský ovládací prvek

Protože tento návod vytvoří komplexní data neumožňující vazbu ovládacího prvku z **uživatelský ovládací prvek**, je nutné přidat **uživatelský ovládací prvek** položku do projektu.

### <a name="to-add-a-user-control-to-the-project"></a>Chcete-li přidat uživatelský ovládací prvek do projektu

1. Z **projektu** nabídce zvolte **přidat uživatelský ovládací prvek**.

1. Typ **ComplexDataGridView** v **název** oblasti a pak klikněte na tlačítko **přidat**.

    **ComplexDataGridView** ovládací prvek je přidán do **Průzkumníku**a otevře v návrháři.

## <a name="design-the-complexdatagridview-control"></a>Návrh ComplexDataGridView ovládací prvek

Tento krok přidává <xref:System.Windows.Forms.DataGridView> do uživatelského ovládacího prvku.

### <a name="to-design-the-complexdatagridview-control"></a>Při návrhu ComplexDataGridView ovládací prvek

- Přetáhněte <xref:System.Windows.Forms.DataGridView> z **sada nástrojů** na návrhovou plochu uživatelského ovládacího prvku.

## <a name="add-the-required-data-binding-attribute"></a>Přidejte požadovaný atribut datová vazba

Pro komplexní ovládací prvky vazbou podpora dat, můžete implementovat <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>.
  
### <a name="to-implement-the-complexbindingproperties-attribute"></a>K implementaci atribut ComplexBindingProperties

1. Přepínač **ComplexDataGridView** řízení zobrazení kódu. (Na **zobrazení** nabídce vyberte možnost **kód**.)

1. Nahraďte kód v `ComplexDataGridView` následujícím kódem:

    [!code-csharp[VbRaddataDisplaying#4](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.cs)]
    [!code-vb[VbRaddataDisplaying#4](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.vb)]

1. Z **sestavení** nabídce zvolte **sestavit řešení**.

## <a name="creating-a-data-source-from-your-database"></a>Vytváření zdroje dat z databáze

Tento krok používá **konfigurace zdroje dat** průvodce vytvořte zdroj dat na základě `Customers` tabulky v ukázkové databázi Northwind.

### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat

1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.

2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **konfigurace zdroje dat** průvodce.

3.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.

4.  Na **zvolit datové připojení** proveďte jednu z následujících akcí:

    - Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

    - Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.

5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data, a pak klikněte na **Další**.

6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.

7.  Na **zvolte databázové objekty** rozbalte **tabulky** uzlu.

8.  Vyberte `Customers` tabulky a potom klikněte na **Dokončit**.

    **NorthwindDataSet** se přidá do projektu a `Customers` se zobrazí v tabulce **zdroje dat** okno.

## <a name="set-the-customers-table-to-use-the-complexdatagridview-control"></a>Nastavit tabulku zákazníků použití ovládacího prvku ComplexDataGridView

V rámci **zdroje dat** okně můžete nastavit ovládací prvek, který má být vytvořen před přetáhnete položky do formuláře.

### <a name="to-set-the-customers-table-to-bind-to-the-complexdatagridview-control"></a>Chcete-li nastavit tabulku zákazníků k vytvoření vazby na ovládací prvek ComplexDataGridView

1. Otevřete **Form1** v návrháři.

1. Rozbalte **zákazníci** uzel v **zdroje dat** okno.

1. Klikněte na šipku rozevíracího seznamu **zákazníci** uzel a zvolte **přizpůsobit**.

1. Vyberte **ComplexDataGridView** ze seznamu **související ovládací prvky** v **možnosti přizpůsobení uživatelského rozhraní dat** dialogové okno.

1. Klikněte na šipku rozevíracího seznamu `Customers` tabulky a vyberte **ComplexDataGridView** ze seznamu ovládacího prvku.

## <a name="add-controls-to-the-form"></a>Přidání ovládacích prvků formuláře

Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.

### <a name="to-create-data-bound-controls-on-the-form"></a>Vytvoření ovládacích prvků vázaných na data ve formuláři

Přetáhněte hlavní **zákazníci** uzlu z **zdroje dat** window do formuláře. Ověřte, zda **ComplexDataGridView** řízení se používá k zobrazení dat v tabulce.  

## <a name="running-the-application"></a>Spuštění aplikace

### <a name="to-run-the-application"></a>Ke spuštění aplikace

Stisknutím klávesy F5 spusťte aplikaci.

## <a name="next-steps"></a>Další kroky

V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete chtít provést po vytvoření ovládacího prvku, který podporuje datovou vazbu. Některé typické další kroky patří:

- Umístění vaše vlastní ovládací prvky v knihovně ovládacího prvku, tak můžete opakovaně použít je v ostatních aplikacích.

- Vytváření ovládacích prvků, které podporují scénáře vyhledávání. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje datovou vazbu vyhledání](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).

## <a name="see-also"></a>Viz také

[Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)  
[Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdrojů dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)  
[Windows Forms – ovládací prvky](/dotnet/framework/winforms/controls/index)
