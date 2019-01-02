---
title: 'Průvodce: Vytvoření datové sady pomocí návrháře datových sad'
ms.date: 09/11/2017
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], walkthroughs
- XML schemas, creating datasets
- data [Visual Studio], Dataset Designer
- Dataset Designer, walkthroughs
- datasets [Visual Basic], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: e79646609bf592b7a8d71d3e0ba8660c65520715
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868512"
---
# <a name="walkthrough-create-a-dataset-with-the-dataset-designer"></a>Průvodce: Vytvoření datové sady pomocí návrháře datových sad

V tomto návodu vytvoříte datovou sadu pomocí **Návrhář Dataset**. Tento článek vás provede procesem vytvoření nového projektu a přidání nové **datovou sadu** položku do ní. Se dozvíte, jak vytvořit tabulky na základě tabulek v databázi bez použití průvodce.

## <a name="prerequisites"></a>Požadavky

Tento návod používá SQL Server Express LocalDB a ukázkové databáze Northwind.

1.  Pokud nemáte SQL Server Express LocalDB, nainstalujte ji z [SQL Server Express stránku pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express), nebo prostřednictvím **instalační program sady Visual Studio**. V aplikaci Visual Studio Instalační služby systému SQL Server Express LocalDB lze nainstalovat jako součást **ukládání a zpracování dat** úlohy, nebo jako jednotlivých komponent.

2.  Instalace ukázkové databáze Northwind pomocí následujících kroků:

    1. V sadě Visual Studio, otevřete **Průzkumník objektů systému SQL Server** okna. (Průzkumník objektů systému SQL Server je nainstalován jako součást **ukládání a zpracování dat** úlohy v instalačním programu sady Visual Studio.) Rozbalte **systému SQL Server** uzlu. Klikněte pravým tlačítkem na instanci LocalDB a vyberte **nový dotaz**.

       Otevře se okno editor dotazů.

    2. Kopírovat [Northwind příkazů jazyka Transact-SQL skriptů](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) do schránky. Tento skript T-SQL vytvoří databázi Northwind úplně od začátku a naplní daty.

    3. Vložte skript T-SQL do editoru dotazů a klikněte na tlačítko **Execute** tlačítko.

       Po chvilce dotaz dokončí provádění a vytvořit databázi Northwind.

## <a name="create-a-new-windows-forms-application-project"></a>Vytvoření nového projektu aplikace Windows Forms

1. V sadě Visual Studio na **souboru** nabídce vyberte možnost **nový** > **projektu**.

2. Rozbalte buď **Visual C#** nebo **jazyka Visual Basic** v levém podokně vyberte **Windows Desktop**.

3. V prostředním podokně, vyberte **aplikace Windows Forms** typ projektu.

4. Pojmenujte projekt **DatasetDesignerWalkthrough**a klikněte na tlačítko **OK**.

     Visual Studio přidá projekt do **Průzkumníka řešení** a nový formulář pro zobrazení v návrháři.

## <a name="add-a-new-dataset-to-the-application"></a>Přidat novou datovou sadu do aplikace

1.  Na **projektu** nabídce vyberte možnost **přidat novou položku**.

     Zobrazí se dialogové okno **Přidat novou položku**.

2.  V levém podokně vyberte **Data**a pak vyberte **datovou sadu** v prostředním podokně.

3.  Zadejte název datové sady **NorthwindDataset**a klikněte na tlačítko **přidat**.

     Visual Studio přidá soubor s názvem **NorthwindDataset.xsd** do projektu a otevře jej v **Návrhář Dataset**.

## <a name="create-a-data-connection-in-server-explorer"></a>Vytvoření datového připojení v Průzkumníku serveru

1.  Na **zobrazení** nabídky, klikněte na tlačítko **Průzkumníka serveru**.

2.  V **Průzkumníka serveru**, klikněte na tlačítko **připojit k databázi** tlačítko.

3.  Vytvořte připojení ke vzorové databázi Northwind.

## <a name="create-the-tables-in-the-dataset"></a>Vytvoření tabulek v datové sadě

Tato část vysvětluje postup přidávání tabulek do datové sady.

### <a name="to-create-the-customers-table"></a>Vytvoření tabulky Zákazníci

1.  Rozbalte datová připojení, kterou jste vytvořili v **Průzkumníka serveru**a potom rozbalte **tabulky** uzlu.

2.  Přetáhněte **zákazníkům** tabulce **Průzkumníka serveru** na **Návrhář Dataset**.

     A **zákazníkům** tabulka dat a **CustomersTableAdapter** jsou přidány do datové sady.

### <a name="to-create-the-orders-table"></a>Vytvoření tabulky objednávek

-   Přetáhněte **objednávky** tabulce **Průzkumníka serveru** na **Návrhář Dataset**.

     **Objednávky** tabulka dat **OrdersTableAdapter**a datová relace mezi **zákazníkům** a **objednávky** tabulky jsou přidány do Datová sada.

### <a name="to-create-the-orderdetails-table"></a>Postup vytvoření tabulky OrderDetails

-   Přetáhněte **OrderDetails** tabulce **Průzkumníka serveru** na **Návrhář Dataset**.

     **OrderDetails** tabulka dat **OrderDetailsTableAdapter**a datová relace mezi **objednávky** a **OrderDetails** tabulky jsou přidány do datové sady.

## <a name="next-steps"></a>Další kroky

-   Uložte datovou sadu.

-   Vyberte položky v **zdroje dat** okno a přetáhněte je na formuláři. Další informace najdete v tématu [ovládací prvky vazby Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).

-   Do instancí TableAdapter přidejte další dotazy.

-   Přidejte logiku ověřování k událostem <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> tabulek dat v datové sadě. Další informace najdete v tématu [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md).

## <a name="see-also"></a>Viz také:

- [Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Ověření dat](../data-tools/validate-data-in-datasets.md)