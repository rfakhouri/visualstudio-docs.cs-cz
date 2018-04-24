---
title: Dotaz datové sady
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 7b1a91cf-8b5a-4fc0-ac36-0dc2d336fa1b
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 03b9e97ab820a65fcd5ec3cb0ea4db2b9cfbde5d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="query-datasets"></a>Dotaz datové sady
K vyhledání konkrétních záznamů v datové sadě, použijte metodu FindBy na DataTable, zapisovat vlastního příkazu foreach smyčku kolekce řádků v tabulce, nebo použijte [LINQ na DataSet](/dotnet/framework/data/adonet/linq-to-dataset).

## <a name="dataset-case-sensitivity"></a>Rozlišování velkých a malých písmen datové sady
V rámci datové sady, tabulky a sloupce, nerozlišují se ve výchozím nastavení – to znamená, že tabulky v datovou sadu s názvem "Zákazníci" může se označovat taky jako "zákazníci". To odpovídá zásady vytváření názvů v mnoha databázemi, včetně systému SQL Server. V systému SQL Server výchozí chování je, že názvy elementů dat nelze rozlišit pouze případu.

> [!NOTE]
>  Na rozdíl od datové sady jsou malá a velká písmena, dokumentů XML, takže datové prvky, které jsou definované v schémata názvů malá a velká písmena. Například protokol schématu umožňuje schéma definovat tabulce s názvem "Zákazníci" a na jinou tabulku s názvem "zákazníci". To může způsobit kolize názvů při schéma, které obsahuje prvky, které se liší pouze v případě se používá ke generování třídu datové sady.

Rozlišování velkých a malých písmen, ale může být faktorem jak data interpretována v rámci datové sady. Například pokud jste filtrování dat v tabulce datovou sadu, kritéria hledání může vrátit odlišné výsledky v závislosti na tom, jestli je porovnání malá a velká písmena. Můžete řídit rozlišování filtrování, vyhledávání a řazení podle nastavení datové sadě <xref:System.Data.DataSet.CaseSensitive%2A> vlastnost. Podle výchozího nastavení dědí všechny tabulky v datové sadě hodnota této vlastnosti. (Tato vlastnost pro každé jednotlivé tabulky můžete přepsat pomocí nastavení v tabulce <xref:System.Data.DataTable.CaseSensitive%2A> vlastnost.)

## <a name="locate-a-specific-row-in-a-data-table"></a>Vyhledejte konkrétní řádek v tabulce dat.

#### <a name="to-find-a-row-in-a-typed-dataset-with-a-primary-key-value"></a>K vyhledání řádku v typové datové sady s hodnotou primární klíče

-   Chcete-li najít řádek, volejte silného typu `FindBy` metoda, která používá primární klíč tabulky.

     V následujícím příkladu `CustomerID` sloupec je primární klíč `Customers` tabulky. To znamená, že vygenerovaného `FindBy` je metoda `FindByCustomerID`. Tento příklad ukazuje, jak přiřadit konkrétní <xref:System.Data.DataRow> proměnné pomocí vygenerovaného `FindBy` metoda.

     [!code-csharp[VbRaddataEditing#18](../data-tools/codesnippet/CSharp/query-datasets_1.cs)]
     [!code-vb[VbRaddataEditing#18](../data-tools/codesnippet/VisualBasic/query-datasets_1.vb)]

#### <a name="to-find-a-row-in-an-untyped-dataset-with-a-primary-key-value"></a>K vyhledání řádku v datové sadě služby bez typu s hodnotou primární klíče

-   Volání <xref:System.Data.DataRowCollection.Find%2A> metodu <xref:System.Data.DataRowCollection> kolekce, předávání primární klíč jako parametr.

     Následující příklad ukazuje, jak deklarovat nový řádek názvem `foundRow` a přiřaďte ho vrácenou hodnotu <xref:System.Data.DataRowCollection.Find%2A> metoda. Pokud je nalezen primární klíč, obsah sloupec indexu 1 se zobrazí v okně se zprávou.

     [!code-csharp[VbRaddataEditing#19](../data-tools/codesnippet/CSharp/query-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#19](../data-tools/codesnippet/VisualBasic/query-datasets_2.vb)]

## <a name="find-rows-by-column-values"></a>Vyhledání řádků podle hodnoty ve sloupcích

#### <a name="to-find-rows-based-on-the-values-in-any-column"></a>K vyhledání řádků na základě hodnot v žádné sloupce

-   Tabulky dat jsou vytvořeny pomocí <xref:System.Data.DataTable.Select%2A> metoda, která vrátí hodnotu pole <xref:System.Data.DataRow>s na základě výrazu předaný <xref:System.Data.DataTable.Select%2A> metoda. Další informace o vytváření platné výrazy, najdete v části "Syntaxe výrazu" stránky <xref:System.Data.DataColumn.Expression%2A> vlastnost.

     Následující příklad ukazuje, jak používat <xref:System.Data.DataTable.Select%2A> metodu <xref:System.Data.DataTable> najít konkrétní řádky.

     [!code-csharp[VbRaddataEditing#20](../data-tools/codesnippet/CSharp/query-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#20](../data-tools/codesnippet/VisualBasic/query-datasets_3.vb)]

## <a name="access-related-records"></a>Access související
Když v datové sadě tabulkami, <xref:System.Data.DataRelation> objekt můžete zpřístupnit související záznamy v jiné tabulce. Například datové sady obsahujícího `Customers` a `Orders` tabulky může být k dispozici.

Můžete použít <xref:System.Data.DataRelation> objekt, který chcete najít související záznamy voláním <xref:System.Data.DataRow.GetChildRows%2A> metodu <xref:System.Data.DataRow> v nadřazené tabulce. Tato metoda vrátí pole souvisejících podřízených záznamů. Nebo můžete volat <xref:System.Data.DataRow.GetParentRow%2A> metodu <xref:System.Data.DataRow> v podřízené tabulce. Tato metoda vrátí hodnotu typu single <xref:System.Data.DataRow> z nadřazené tabulce.

Tato stránka obsahuje příklady použití typové datové sady. Informace o navigace relací v netypové datové sady najdete v tématu [navigace DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations).

> [!NOTE]
>  Pokud pracujete v aplikaci Windows Forms a používání funkcí datové vazby k zobrazení dat, generovaném formuláři může poskytnout dostatek funkce pro vaši aplikaci. Další informace najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Konkrétně, najdete v části [vztahy v datových sadách](relationships-in-datasets.md).

Následující příklady kódu ukazují, jak se orientovat nahoru a dolů vztahy v typových datových sadách. Příklady použití kódu zadali <xref:System.Data.DataRow>s (`NorthwindDataSet.OrdersRow`) a vygenerovaný FindBy*PrimaryKey* (`FindByCustomerID`) metody pro vyhledání požadovaného řádku a vrátí související záznamy. Příklady zkompilování a spuštění správně pouze v případě, že máte:

-   Instance datovou sadu s názvem `NorthwindDataSet` s `Customers` tabulky.

-   `Orders` Tabulky.

-   Relace s názvem `FK_Orders_Customers`týkající se dvě tabulky.

Kromě toho obě tabulky musí být vyplněny data pro všechny záznamy, který se má vrátit.

#### <a name="to-return-the-child-records-of-a-selected-parent-record"></a>Vrátí podřízené záznamy vybrané nadřazené záznamu

-   Volání <xref:System.Data.DataRow.GetChildRows%2A> metoda konkrétní `Customers` data řádek a vrátí řádky z pole `Orders` tabulky:

     [!code-csharp[VbRaddataDatasets#6](../data-tools/codesnippet/CSharp/query-datasets_4.cs)]
     [!code-vb[VbRaddataDatasets#6](../data-tools/codesnippet/VisualBasic/query-datasets_4.vb)]

#### <a name="to-return-the-parent-record-of-a-selected-child-record"></a>Chcete-li se vrátit nadřazený záznam na vybraný podřízený záznam

-   Volání <xref:System.Data.DataRow.GetParentRow%2A> metoda konkrétní `Orders` řádek dat a vrátí jeden řádek z `Customers` tabulky:

     [!code-csharp[VbRaddataDatasets#7](../data-tools/codesnippet/CSharp/query-datasets_5.cs)]
     [!code-vb[VbRaddataDatasets#7](../data-tools/codesnippet/VisualBasic/query-datasets_5.vb)]

## <a name="see-also"></a>Viz také

- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)