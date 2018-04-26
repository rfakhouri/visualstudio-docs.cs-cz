---
title: Vytvoření uživatelského ovládacího prvku, který podporuje jednoduchou datovou vazbu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a484388223b7dae62f165e13b2fc75368b0e642f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>Vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje jednoduchou datovou vazbu
Při zobrazení dat ve formulářích v aplikacích Windows, můžete zvolit existující ovládacích prvků z **sada nástrojů**, nebo můžete vytvořit vlastní ovládací prvky, pokud vaše aplikace vyžaduje funkce, která není k dispozici v standardní ovládací prvky. Tento návod ukazuje postup vytvoření ovládacího prvku, který implementuje <xref:System.ComponentModel.DefaultBindingPropertyAttribute>. Určuje, které implementují <xref:System.ComponentModel.DefaultBindingPropertyAttribute> může obsahovat jednu vlastnost, která mohou být vázány na data. Tyto prvky jsou podobné <xref:System.Windows.Forms.TextBox> nebo <xref:System.Windows.Forms.CheckBox>.

 Další informace o vytváření řízení najdete v tématu [vývoj ovládacích prvků Windows Forms v době návrhu](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).

 Při vytváření ovládacích prvků pro použití v scénáře datových vazeb, měli byste jeden z následujících atributů datové vazby implementovat:

|Používání atributu datová vazba|
|-----------------------------------|
|Implementace <xref:System.ComponentModel.DefaultBindingPropertyAttribute> na jednoduché ovládací prvky, jako <xref:System.Windows.Forms.TextBox>, který jeden sloupec (nebo vlastnost) dat zobrazit. (Tento proces je popsaný v této stránce návod.)|
|Implementace <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> na ovládací prvky, jako <xref:System.Windows.Forms.DataGridView>, který zobrazí seznamy (nebo tabulky) data. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje rozšířené datové vazby](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|
|Implementace <xref:System.ComponentModel.LookupBindingPropertiesAttribute> na ovládací prvky, jako je <xref:System.Windows.Forms.ComboBox>, které zobrazí seznamy (nebo tabulky) data, ale také muset jeden sloupec nebo vlastnost k dispozici. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje datovou vazbu vyhledání](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|

 Tento návod vytvoří jednoduchý ovládací prvek, který zobrazuje data z jednoho sloupce v tabulce. Tento příklad používá `Phone` sloupec `Customers` tabulku z ukázková databáze Northwind. Pomocí jednoduchého uživatelského ovládacího prvku zobrazí zákazníků telefonní čísla ve standardním formátu telefonní číslo, <xref:System.Windows.Forms.MaskedTextBox> a nastavení masky na telefonní číslo.

 Během tohoto návodu se dozvíte, jak:

-   Vytvořte novou **formulářové aplikace Windows**.

-   Přidejte nový **uživatelský ovládací prvek** do projektu.

-   Vizuální návrh uživatelského ovládacího prvku.

-   Implementace `DefaultBindingProperty` atribut.

-   Vytvořit datovou sadu s **konfigurace zdroje dat** průvodce.

-   Nastavte **Phone** sloupec v **zdroje dat** okna nový ovládací prvek.

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

4. Název projektu **SimpleControlWalkthrough**a potom zvolte **OK**.

     **SimpleControlWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.

## <a name="add-a-user-control-to-the-project"></a>Do projektu přidejte uživatelský ovládací prvek
 Tento návod vytvoří jednoduchý data neumožňující vazbu ovládacího prvku z **uživatelský ovládací prvek**, proto přidat **uživatelský ovládací prvek** položkou **SimpleControlWalkthrough** projektu.

#### <a name="to-add-a-user-control-to-the-project"></a>Chcete-li přidat uživatelský ovládací prvek do projektu

1.  Z **projektu** nabídce zvolte **přidat uživatelský ovládací prvek**.

2.  Typ `PhoneNumberBox` název oblasti, a klikněte na **přidat**.

     **PhoneNumberBox** ovládací prvek je přidán do **Průzkumníku**a otevře v návrháři.

## <a name="design-the-phonenumberbox-control"></a>Návrh PhoneNumberBox ovládací prvek
 Tento názorný postup rozšíří na stávajících <xref:System.Windows.Forms.MaskedTextBox> vytvořit `PhoneNumberBox` ovládacího prvku.

#### <a name="to-design-the-phonenumberbox-control"></a>Při návrhu PhoneNumberBox ovládací prvek

1.  Přetáhněte <xref:System.Windows.Forms.MaskedTextBox> z **sada nástrojů** na návrhovou plochu uživatelského ovládacího prvku.

2.  Vyberte inteligentních značek v <xref:System.Windows.Forms.MaskedTextBox> jste právě přetáhli a zvolte **nastavit maska**.

3.  Vyberte **telefonní číslo** v **vstupní maska** dialogové okno a klikněte na tlačítko **OK** nastavit maska.

## <a name="add-the-required-data-binding-attribute"></a>Přidejte požadovaný atribut datová vazba
 Pro jednoduché ovládací prvky vazby dat tuto podporu, implementovat <xref:System.ComponentModel.DefaultBindingPropertyAttribute>.

#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>K implementaci atribut DefaultBindingProperty

1.  Přepínač `PhoneNumberBox` řízení zobrazení kódu. (Na **zobrazení** nabídce zvolte **kód**.)

2.  Nahraďte kód v `PhoneNumberBox` následujícím kódem:

     [!code-csharp[VbRaddataDisplaying#3](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#3](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.vb)]

3.  Z **sestavení** nabídce zvolte **sestavit řešení**.

## <a name="create-a-data-source-from-your-database"></a>Vytvoření zdroje dat z databáze
 Tento krok používá **konfigurace zdroje dat**průvodce vytvořte zdroj dat na základě `Customers` tabulky v ukázkové databázi Northwind. Musíte mít přístup k ukázková databáze Northwind k vytvoření připojení. Informace o nastavení ukázková databáze Northwind najdete v tématu [postupy: Instalace ukázkové databáze](../data-tools/installing-database-systems-tools-and-samples.md).

#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat

1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**.

2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **konfigurace zdroje dat** průvodce.

3.  Na **zvolte typ zdroje dat** vyberte **databáze**a potom klikněte na **Další**.

4.  Na **zvolit datové připojení** proveďte jednu z následujících:

    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.

5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data, a pak klikněte na **Další**.

6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.

7.  Na **zvolte databázové objekty** rozbalte **tabulky** uzlu.

8.  Vyberte `Customers` tabulky a potom klikněte na **Dokončit**.

     **NorthwindDataSet** se přidá do projektu a `Customers` se zobrazí v tabulce **zdroje dat** okno.

## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>Nastavit telefon sloupec použití ovládacího prvku PhoneNumberBox
 V rámci **zdroje dat** okně můžete nastavit ovládací prvek, který má být vytvořen před přetáhnete položky do formuláře.

#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>Chcete-li nastavit sloupci phone k vytvoření vazby na ovládací prvek PhoneNumberBox

1.  Otevřete **Form1** v návrháři.

2.  Rozbalte **zákazníci** uzel v **zdroje dat** okno.

3.  Klikněte na šipku rozevíracího seznamu **zákazníci** uzel a zvolte **podrobnosti** ze seznamu řízení.

4.  Klikněte na šipku rozevíracího seznamu **Phone** sloupce a vyberte **přizpůsobit**.

5.  Vyberte **PhoneNumberBox** ze seznamu **související ovládací prvky** v **možnosti přizpůsobení uživatelského rozhraní dat** dialogové okno.

6.  Klikněte na šipku rozevíracího seznamu **Phone** sloupce a vyberte **PhoneNumberBox**.

## <a name="add-controls-to-the-form"></a>Přidání ovládacích prvků formuláře
 Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** window do formuláře.

#### <a name="to-create-data-bound-controls-on-the-form"></a>Vytvoření ovládacích prvků vázaných na data ve formuláři

-   Přetáhněte hlavní **zákazníkům** uzlu z **zdroje dat** window do formuláře a ověřte, že `PhoneNumberBox` řízení se používá k zobrazení dat v `Phone` sloupce.

     Ovládací prvky vázané na data s popisky jsou zobrazena na formuláři, společně s pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.

## <a name="run-the-application"></a>Spuštění aplikace

#### <a name="to-run-the-application"></a>Ke spuštění aplikace

-   Stisknutím klávesy F5 spusťte aplikaci.

## <a name="next-steps"></a>Další kroky
 V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete chtít provést po vytvoření ovládacího prvku, který podporuje datovou vazbu. Některé typické další kroky patří:

-   Umístění vaše vlastní ovládací prvky v knihovně ovládacího prvku, tak můžete opakovaně použít je v ostatních aplikacích.

-   Vytváření ovládacích prvků, které podporují složitější scénáře datových vazeb. Další informace najdete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje rozšířené datové vazby](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) a [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje datovou vazbu vyhledání](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdrojů dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)