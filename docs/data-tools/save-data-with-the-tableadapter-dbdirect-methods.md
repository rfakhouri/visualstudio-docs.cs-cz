---
title: "Ukládání dat pomocí TableAdapter DBDirect metody | Microsoft Docs"
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
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 3ed52a167b607236b8493e4c8c1736ee597162b9
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>Ukládání dat pomocí TableAdapter DBDirect metody
Tento názorný postup obsahuje podrobné pokyny ke spouštění příkazů SQL přímo s databází pomocí metod TableAdapter DBDirect. Metod TableAdapter DBDirect zadejte jemné úroveň kontroly nad aktualizace vaší databáze. Můžete je použít ke spuštění konkrétních příkazů SQL a uložených procedur voláním jednotlivých `Insert`, `Update`, a `Delete` metody podle potřeby vaší aplikace (oproti přetížené `Update` metodu, která provede aktualizace INSERT a DELETE příkazy všechny v jednom volání).  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Vytvořte novou **formulářové aplikace Windows**.  
  
-   Vytvořit a nakonfigurovat datová sada se [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Vyberte ovládací prvek, který má být vytvořen ve formuláři při přetáhnete položky z **zdroje dat** okno. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Vytvoření formuláře vázané na data tak, že přetáhnete položky z **zdroje dat** window do formuláře.  
  
-   Přidejte metody přímo přístup k databázi a provést vložení, aktualizace a odstranění...  
  
## <a name="prerequisites"></a>Požadavky  
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  
  
1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.  
  
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

4. Název projektu **TableAdapterDbDirectMethodsWalkthrough**a potom zvolte **OK**. 
  
     **TableAdapterDbDirectMethodsWalkthrough** je vytvořen a přidán do projektu **Průzkumníku řešení**.  
  
## <a name="create-a-data-source-from-your-database"></a>Vytvoření zdroje dat z databáze  
 Tento krok používá **Průvodce konfigurací zdroje dat** vytvořit zdroj dat na základě `Region` tabulky v ukázkové databázi Northwind. Musíte mít přístup k ukázková databáze Northwind k vytvoření připojení. Informace o nastavení ukázková databáze Northwind najdete v tématu [postupy: Instalace ukázkové databáze](../data-tools/installing-database-systems-tools-and-samples.md).  
  
#### <a name="to-create-the-data-source"></a>Vytvoření zdroje dat  
  
1.  Na **Data** nabídce vyberte možnost **zobrazit zdroje dat**.  
  
2.  V **zdroje dat** vyberte **přidat nový zdroj dat** spustit **Průvodce konfigurací zdroje dat**.  
  
3.  Na **zvolte typ zdroje dat** obrazovku, vyberte **databáze**a potom vyberte **Další**.  
  
4.  Na **zvolit datové připojení** obrazovky, proveďte jednu z následujících akcí:  
  
    -   Pokud je připojení dat k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.  
  
         -nebo-  
  
    -   Vyberte **nové připojení** ke spuštění **přidat či upravit připojení** dialogové okno.  
  
5.  Pokud vaše databáze vyžaduje heslo, vyberte možnost obsahují citlivá data a pak vyberte **Další**.  
  
6.  Na **uložit připojovací řetězec do konfiguračního souboru aplikace** obrazovku, vyberte **Další**.  
  
7.  Na **zvolte databázové objekty** obrazovky, rozbalte **tabulky** uzlu.  
  
8.  Vyberte `Region` tabulky a potom vyberte **Dokončit**.  
  
     **NorthwindDataSet** se přidá do projektu a `Region` se zobrazí v tabulce **zdroje dat** okno.  
  
## <a name="add-controls-to-the-form-to-display-the-data"></a>Přidání ovládacích prvků formuláře pro zobrazení dat  
 Vytvořit ovládací prvky vázané na data tak, že přetáhnete položky z **zdroje dat** okna do svého formuláře.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Chcete-li vytvořit data vázané ovládací prvky na formuláři Windows  
  
-   Přetáhněte hlavní **oblast** uzlu z **zdroje dat** window do formuláře.  
  
     A <xref:System.Windows.Forms.DataGridView> řízení a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>) pro procházení záznamů jsou zobrazena na formuláři. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `RegionTableAdapter`, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>Přidání tlačítka, která bude volat metody jednotlivých TableAdapter DbDirect  
  
1.  Přetáhněte tři <xref:System.Windows.Forms.Button> z ovládací prvky **sada nástrojů** na **Form1** (dole **RegionDataGridView**).  
  
2.  Nastavte následující **název** a **Text** vlastnosti na každé tlačítko.  
  
    |Název|Text|  
    |----------|----------|  
    |`InsertButton`|**Vložení**|  
    |`UpdateButton`|**Aktualizace**|  
    |`DeleteButton`|**Odstranit**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>Chcete-li přidat kód pro vkládání nových záznamů do databáze  
  
1.  Vyberte **InsertButton** vytvoření obslužné rutiny události pro událost click a otevřete formulář v editoru kódu.  
  
2.  Nahraďte `InsertButton_Click` obslužné rutiny události s následujícím kódem:  
  
     [!code-vb[VbRaddataSaving#1](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_1.vb)]
     [!code-csharp[VbRaddataSaving#1](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_1.cs)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>Přidání kódu k aktualizaci záznamů v databázi  
  
1.  Dvakrát klikněte **UpdateButton** vytvoření obslužné rutiny události pro událost click a otevřete formulář v editoru kódu.  
  
2.  Nahraďte `UpdateButton_Click` obslužné rutiny události s následujícím kódem:  
  
     [!code-vb[VbRaddataSaving#2](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_2.vb)]
     [!code-csharp[VbRaddataSaving#2](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_2.cs)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>Chcete-li přidat kód můžete odstranit záznamy z databáze  
  
1.  Vyberte **DeleteButton** vytvoření obslužné rutiny události pro událost click a otevřete formulář v editoru kódu.  
  
2.  Nahraďte `DeleteButton_Click` obslužné rutiny události s následujícím kódem:  
  
     [!code-vb[VbRaddataSaving#3](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_3.vb)]
     [!code-csharp[VbRaddataSaving#3](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_3.cs)]  
  
## <a name="run-the-application"></a>Spuštění aplikace  
  
#### <a name="to-run-the-application"></a>Ke spuštění aplikace  
  
-   Vyberte **F5** ke spuštění aplikace.  
  
-   Vyberte **vložit** tlačítko a ověřte, že se zobrazí nový záznam v mřížce.  
  
-   Vyberte **aktualizace** tlačítko a ověřte, zda záznam aktualizován v mřížce.  
  
-   Vyberte **odstranit** tlačítko a ověřte, že záznam odebrána z mřížky.  
  
## <a name="next-steps"></a>Další kroky  
 V závislosti na požadavcích vaší aplikace existuje několik kroků, které můžete chtít provést po vytvoření vázané na data formuláře. Mezi vylepšení, která je možné pro tento návod provést, patří:  
  
-   Přidání funkce vyhledávání do formuláře.  
  
-   Přidání další tabulky k datové sadě výběrem **konfigurace sady dat pomocí průvodce** uvnitř **zdroje dat** okno. Můžete přidat ovládací prvky, které zobrazení souvisejících dat přetažením související uzly do formuláře. Další informace najdete v tématu [vztahy v datových sadách](relationships-in-datasets.md).  
  
## <a name="see-also"></a>Viz také  
 [Uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md)