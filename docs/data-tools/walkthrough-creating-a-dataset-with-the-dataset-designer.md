---
title: "Návod: Vytvoření datové sady pomocí návrháře Dataset | Microsoft Docs"
ms.custom: 
ms.date: 09/11/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- datasets [Visual Basic], walkthroughs
- XML schemas, creating datasets
- data [Visual Studio], Dataset Designer
- Dataset Designer, walkthroughs
- datasets [Visual Basic], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f826f7d33a8d35719afacb053995629433b27642
ms.sourcegitcommit: e951faab601f5c05ad6606d8fd0cd2059fc4cc25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="walkthrough-creating-a-dataset-with-the-dataset-designer"></a>Návod: Vytvoření datové sady pomocí Návrháře DataSet

V tomto návodu vytvoříte datové sady pomocí **návrháře Dataset**. Bude vás provede procesem vytvoření nového projektu a přidání nového **datovou sadu** položky k němu. Naučíte se vytvářet tabulky na základě tabulek z databáze bez použití průvodce.  

Úkoly v tomto návodu zahrnují:  

-   Vytvoření nové **formulářové aplikace Windows** projektu.  

-   Přidání prázdnou **datovou sadu** položku do projektu.  

-   Vytváření a konfiguraci zdroje dat v aplikaci podle budovy datová sada se **návrháře Dataset**.  
 
-   Vytvoření připojení k databázi Northwind v **Průzkumníka serveru**.  

-   Vytváření tabulek pomocí instancí TableAdapter v datové sadě založené na tabulkách v databázi.  

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
Tento návod používá SQL Server Express LocalDB a ukázková databáze Northwind.  
  
1.  Pokud nemáte SQL serveru Express LocalDB, nainstalovat buď z [stránce pro stažení edice serveru SQL](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), nebo pomocí **instalační program Visual Studio**. V instalačním programu Visual Studio se může nainstalovat SQL Server Express LocalDB jako součást **úložiště dat a zpracování** zatížení, nebo jako jednotlivých součástí.  
  
2.  Ukázková databáze Northwind nainstalujte pomocí následujících kroků:  

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okno. (Průzkumník objektů systému SQL Server je nainstalován jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na vaší instanci LocalDB a vyberte **nový dotaz...** .  

       Otevře se okno editoru dotazů.  

    2. Kopírování [Northwind Transact-SQL skriptu](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind od začátku a naplní s daty.  

    3. Vložit do editoru dotazů skriptu T-SQL a potom vyberte **Execute** tlačítko.  

       Po krátkou dobu dotaz dokončí provádění a vytvoření databáze Northwind.  
  
## <a name="creating-a-new-windows-forms-application-project"></a>Vytvoření nového projektu aplikace Windows Forms  
  
#### <a name="to-create-a-new-windows-forms-application-project"></a>Chcete-li vytvořit nový projekt aplikace Windows Forms  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **DatasetDesignerWalkthrough**a potom zvolte **OK**.  
  
     Visual Studio. přidá projekt **Průzkumníku řešení** a zobrazení nového formuláře v návrháři.  
  
## <a name="adding-a-new-dataset-to-the-application"></a>Přidání nové datové sady do aplikace  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>Postup přidání nové položky datové sady do projektu  
  
1.  Na **projektu** nabídce vyberte možnost **přidat novou položku...** .  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
2.  V levém podokně vyberte **Data**, pak vyberte **datovou sadu** v prostředním podokně.  
  
3.  Název datové sady **NorthwindDataset**a potom zvolte **přidat**.  
  
     Visual Studio. přidá do souboru s názvem **NorthwindDataset.xsd** do projektu a otevře ji v **návrháře Dataset**.  
  
## <a name="creating-a-data-connection-in-server-explorer"></a>Vytvoření datového připojení v Průzkumníku serveru  
  
#### <a name="to-create-a-connection-to-the-northwind-database"></a>Postup vytvoření připojení k databázi Northwind  
  
1.  Na **zobrazení** nabídky, klikněte na tlačítko **Průzkumníka serveru**.  
  
2.  V **Průzkumníka serveru**, klikněte **připojit k databázi** tlačítko.  
  
3.  Vytvořte připojení ke vzorové databázi Northwind.  
  
## <a name="creating-the-tables-in-the-dataset"></a>Vytváření tabulek v datové sadě  
Tato část vysvětluje postup přidání tabulky do datové sady.  
  
#### <a name="to-create-the-customers-table"></a>Vytvoření tabulky Zákazníci  
  
1.  Rozbalte datové připojení, kterou jste vytvořili v **Průzkumníka serveru**a potom rozbalte **tabulky** uzlu.  
  
2.  Přetáhněte **zákazníci** tabulce **Průzkumníka serveru** na **návrháře Dataset**.  
  
     A **zákazníci** tabulku dat a **CustomersTableAdapter** jsou přidány do datové sady.  
  
#### <a name="to-create-the-orders-table"></a>Vytvoření tabulky objednávek  
  
-   Přetáhněte **objednávky** tabulce **Průzkumníka serveru** na **návrháře Dataset**.  
  
     **Objednávky** datová tabulka **OrdersTableAdapter**a data vztah mezi **zákazníci** a **objednávky** tabulky jsou přidány do datové sady.  
  
#### <a name="to-create-the-orderdetails-table"></a>Postup vytvoření tabulky OrderDetails  
  
-   Přetáhněte **pořadí podrobnosti** tabulce **Průzkumníka serveru** na **návrháře Dataset**.  
  
     **Pořadí podrobnosti** datová tabulka **OrderDetailsTableAdapter**a data vztah mezi **objednávky** a **Rozpis objednávek** tabulky budou přidány do datové sady.  
  
## <a name="next-steps"></a>Další kroky  
  
### <a name="to-add-functionality-to-your-application"></a>Přidání funkce do vaší aplikace  
  
-   Uložte datovou sadu.  
  
-   Vyberte položky v **zdroje dat** okna a přetáhněte je na formuláři. Další informace najdete v tématu [vazby Windows Forms – ovládací prvky k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).  
  
-   Do instancí TableAdapter přidejte další dotazy. 
  
-   Přidejte logiku ověřování k událostem <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> tabulek dat v datové sadě. Další informace najdete v tématu [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md).  
  
## <a name="see-also"></a>Viz také
[Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)  
[Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
[Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)   
[Ověřování dat](../data-tools/validate-data-in-datasets.md)   
[Ukládání dat](../data-tools/saving-data.md)