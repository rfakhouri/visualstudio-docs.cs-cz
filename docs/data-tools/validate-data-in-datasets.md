---
title: Ověřování dat v datových sadách
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataTable.ColumnChanging
- System.Data.DataTable.ColumnChanging
- System.Data.DataTable.RowChanging
- DataTable.RowChanging
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data validation, datasets
- data validation
- validating data, datasets
- updating datasets, validating data
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c8986ce9e2ee1ff171a524b0a402a1e44b70ca06
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="validate-data-in-datasets"></a>Ověřování dat v datových sadách
Ověřování dat je proces ověření, která zadaných do datových objektů v souladu s omezeními ve schématu datové sady. Proces ověření také potvrdí, že tyto hodnoty jsou následující pravidla, které byly vytvořeny pro vaši aplikaci. Je vhodné ověřit data před odesláním aktualizací do základní databáze. Tím se snižuje chyby, jakož i potenciální počet odezev mezi aplikace a databáze.

Můžete potvrdit, že data, která probíhá zápis do datové sady je platná, a vytváření ověřovacích kontrol do datové sady, sám sebe. Datové sady můžete zkontrolovat dat bez ohledu na to, jak se provádí aktualizace – jestli přímo z ovládacích prvků ve formuláři, v rámci komponenty, nebo jiným způsobem. Datová sada je součástí vaší aplikace (na rozdíl od databáze back-end), je logický místo, kde můžete vytvářet ověření specifické pro aplikaci.

Nejlepší místo k přidání ověřování do aplikace je v souboru třídu datovou sadu. V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], otevřete **návrháře Dataset** a dvakrát klikněte na sloupec nebo tabulka, pro který chcete vytvořit ověření. Tato akce automaticky vytvoří <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> obslužné rutiny události.

## <a name="validate-data"></a>Ověřování dat
 Ověření v rámci datové sady se dá udělat následujícími způsoby:

-   Vytvořením vlastního ověřování konkrétní aplikace můžete zkontrolovat hodnoty v jednotlivých datových sloupec během změny.  Další informace najdete v tématu [postupy: ověření dat během úprav sloupců](validate-data-in-datasets.md).

-   Vytvořením vlastní ověření specifické pro aplikaci, který můžete zkontrolovat dat na hodnoty během celého datového řádek mění. Další informace najdete v tématu [postupy: ověření dat během úprav řádků](validate-data-in-datasets.md).

-   Po vytvoření klíče, jedinečné omezení, a tak dále jako součást definice skutečné schématu datové sady.

-   Nastavením vlastnosti <xref:System.Data.DataColumn> objektu, například <xref:System.Data.DataColumn.MaxLength%2A>, <xref:System.Data.DataColumn.AllowDBNull%2A>, a <xref:System.Data.DataColumn.Unique%2A>.

Několik událostí jsou vydané <xref:System.Data.DataTable> objektu při změně dochází v záznamu:

-   <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.ColumnChanged> události jsou vyvolány během a po každé změně pro jednotlivé sloupce. <xref:System.Data.DataTable.ColumnChanging> Událostí je užitečné, když chcete ověřit změny v určité sloupce. Informace o navrhované změny je předat jako argument k události.
-   <xref:System.Data.DataTable.RowChanging> a <xref:System.Data.DataTable.RowChanged> události jsou vyvolány během a po všech změn v řádku. <xref:System.Data.DataTable.RowChanging> Je další obecné události. Znamená že změnu dochází někde v řádku, ale nevíte, které sloupce se změnila.

Ve výchozím nastavení vyvolá každé změně ke sloupci, proto čtyři události. První je <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.ColumnChanged> události pro konkrétní sloupec, který mění se. Dále jsou <xref:System.Data.DataTable.RowChanging> a <xref:System.Data.DataTable.RowChanged> události. Pokud více změn jsou prováděny na řádek, události, bude vyvolána u každé změny.

> [!NOTE]
>  Řádek dat <xref:System.Data.DataRow.BeginEdit%2A> metoda vypne <xref:System.Data.DataTable.RowChanging> a <xref:System.Data.DataTable.RowChanged> události po každé změně jednotlivé sloupce. V takovém případě není vyvolá událost, dokud <xref:System.Data.DataRow.EndEdit%2A> byla volána metoda, když <xref:System.Data.DataTable.RowChanging> a <xref:System.Data.DataTable.RowChanged> události jsou vyvolány pouze jednou. Další informace najdete v tématu [vypnutí omezení při naplňování datové sady](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

Události, kterou zvolíte závisí na tom, jak granulární chcete ověření, který má být. Pokud je důležité catch chybu, okamžitě až sloupec změní, vytvářet ověření pomocí <xref:System.Data.DataTable.ColumnChanging> událostí. Jinak použijte <xref:System.Data.DataTable.RowChanging> událost, která může mít za následek zachytávání najednou několik chyb. Kromě toho, pokud jsou strukturovaná data tak, aby ověření na základě obsahu jiný sloupec hodnoty jednoho sloupce, pak ověření vaší během <xref:System.Data.DataTable.RowChanging> událostí.

Když jsou aktualizovány záznamy <xref:System.Data.DataTable> objekt vyvolává události, které mohou reagovat na změny dochází a po provedení změn.

Pokud vaše aplikace používá typové datové sady, můžete vytvořit obslužné rutiny událostí silného typu. Bude přidáno čtyři další typu události, které můžete vytvořit obslužné rutiny pro: `dataTableNameRowChanging`, `dataTableNameRowChanged`, `dataTableNameRowDeleting`, a `dataTableNameRowDeleted`. Tyto obslužné rutiny typu událostí předat argument, který obsahuje názvy sloupců tabulky, které usnadňují kódu k zápisu a čtení.

## <a name="data-update-events"></a>Aktualizovat data události

|Událost|Popis|
|-----------|-----------------|
|<xref:System.Data.DataTable.ColumnChanging>|Mění se hodnota ve sloupci. Událost předá řádků a sloupců, společně s navrhované novou hodnotu.|
|<xref:System.Data.DataTable.ColumnChanged>|Hodnota ve sloupci byl změněn. Událost předá řádků a sloupců, společně s navrhované hodnoty.|
|<xref:System.Data.DataTable.RowChanging>|Změny, které byly provedeny <xref:System.Data.DataRow> objektu se chystáte potvrzeny zpět do datové sady. Pokud nebyly volána <xref:System.Data.DataRow.BeginEdit%2A> metody <xref:System.Data.DataTable.RowChanging> událost se vyvolá u každé změny na sloupec ihned po <xref:System.Data.DataTable.ColumnChanging> událost byla vyvolána. Pokud jste volali metodu <xref:System.Data.DataRow.BeginEdit%2A> před prováděním změn, <xref:System.Data.DataTable.RowChanging> událost se vyvolá, pouze v případě, že zavoláte <xref:System.Data.DataRow.EndEdit%2A> metoda.<br /><br /> Událost předá řádek, společně s hodnotu určující, jaký typ akce (Změna, insert a tak dále) právě probíhá.|
|<xref:System.Data.DataTable.RowChanged>|Řádek byl změněn. Událost předá řádek, společně s hodnotu určující, jaký typ akce (Změna, insert a tak dále) právě probíhá.|
|<xref:System.Data.DataTable.RowDeleting>|Probíhá odstranění řádku. Událost předá řádek, společně s hodnotu určující, jaký typ akce (odstranit) právě probíhá.|
|<xref:System.Data.DataTable.RowDeleted>|Řádek byl odstraněn. Událost předá řádek, společně s hodnotu určující, jaký typ akce (odstranit) právě probíhá.|

<xref:System.Data.DataTable.ColumnChanging>, <xref:System.Data.DataTable.RowChanging>, A <xref:System.Data.DataTable.RowDeleting> události jsou vyvolány během procesu aktualizace. Tyto události můžete použít k ověření dat nebo provádět jiné typy zpracování. Protože je aktualizace v procesu během těchto událostí, můžete ji zrušit pomocí došlo k výjimce, což zabrání aktualizaci z dokončení.

<xref:System.Data.DataTable.ColumnChanged>, <xref:System.Data.DataTable.RowChanged> a <xref:System.Data.DataTable.RowDeleted> události jsou události oznámení, které se vyvolá, když aktualizace byl úspěšně dokončen. Tyto události jsou užitečné, pokud chcete provádět další akce v závislosti na úspěšná aktualizace.

## <a name="validate-data-during-column-changes"></a>Ověřování dat během úprav sloupců

> [!NOTE]
>  **Návrháře Dataset** vytvoří částečné třídy ověřování, které lze přidat logiku do datové sady. Datová sada generovaném není odstranit nebo změnit spuštěním kódu třídu.

Můžete ověřit data při změně hodnoty ve sloupci dat podle neodpovídá na požadavky <xref:System.Data.DataTable.ColumnChanging> událostí. Po vyvolání, tato událost předá argument události (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>), obsahuje hodnotu, která je navrhované pro aktuální sloupec. Podle obsahu `e.ProposedValue`, můžete:

-   Pomocí tohoto postupu nic přijměte navrhované hodnoty.

-   Odmítnout navržená hodnota nastavením chyba sloupce (<xref:System.Data.DataRow.SetColumnError%2A>) z v rámci obslužné rutiny události Změna sloupce.

-   Volitelně můžete použít <xref:System.Windows.Forms.ErrorProvider> ovládací prvek zobrazí chybovou zprávu pro uživatele. Další informace najdete v tématu [ErrorProvider – komponenta](/dotnet/framework/winforms/controls/errorprovider-component-windows-forms).

Ověření lze také provést během <xref:System.Data.DataTable.RowChanging> událostí.

## <a name="validate-data-during-row-changes"></a>Ověřování dat během úprav řádků
Můžete napsat kód pro ověřte, že všechny sloupce, které chcete ověřit obsahuje data, která splňuje požadavky vaší aplikace. Proveďte nastavením sloupce, který se označuje, že obsahuje chybu pokud navrhované hodnota nemůže být přijata. Následující příklady nastavena na sloupec chybu při `Quantity` sloupec je 0 nebo menší. Obslužné rutiny událostí Změna řádku by měl vypadat podobně jako následující příklady.

#### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>Chcete-li ověřit data při řádek změny (Visual Basic)

1.  Otevřete datovou sadu v **návrháře Dataset**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Dvakrát klikněte na záhlaví tabulky, kterou chcete ověřit. Tato akce automaticky vytvoří <xref:System.Data.DataTable.RowChanging> obslužnou rutinu události <xref:System.Data.DataTable> v souboru částečné třídy datovou sadu.

    > [!TIP]
    >  Dvakrát klikněte na panel nalevo od názvu tabulky k vytvoření obslužné rutiny události Změna řádek. Pokud dvakrát kliknete na název tabulky, můžete ji upravit.

     [!code-vb[VbRaddataValidating#3](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_1.vb)]

#### <a name="to-validate-data-when-a-row-changes-c"></a>Ověřit data, kdy se změní řádek (C#)

1.  Otevřete datovou sadu v **návrháře Dataset**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Dvakrát klikněte na záhlaví tabulky, kterou chcete ověřit. Tato akce vytvoří soubor částečné třídy pro <xref:System.Data.DataTable>.

    > [!NOTE]
    >  **Návrháře Dataset** nevytvoří automaticky obslužné rutiny události pro <xref:System.Data.DataTable.RowChanging> událostí. Je nutné vytvořit metodu ke zpracování <xref:System.Data.DataTable.RowChanging> událostí a spuštění kódu spojit události v inicializační metoda v tabulce.

3.  Zkopírujte následující kód do třídu:

    ```csharp
    public override void EndInit()
    {
        base.EndInit();
        Order_DetailsRowChanging += TestRowChangeEvent;
    }

    public void TestRowChangeEvent(object sender, Order_DetailsRowChangeEvent e)
    {
        if ((short)e.Row.Quantity <= 0)
        {
            e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
        }
        else
        {
            e.Row.SetColumnError("Quantity", "");
        }
    }
    ```

## <a name="to-retrieve-changed-rows"></a>K načítání změněných řádků
Má každý řádek v tabulce dat <xref:System.Data.DataRow.RowState%2A> vlastnost, která uchovává informace o aktuálním stavu příslušném řádku s použitím hodnoty v <xref:System.Data.DataRowState> výčtu. Můžete se vrátit změněných řádků z tabulky sadu dat nebo dat podle volání `GetChanges` metodu <xref:System.Data.DataSet> nebo <xref:System.Data.DataTable>. Můžete ověřit, že existují změny před voláním `GetChanges` voláním <xref:System.Data.DataSet.HasChanges%2A> metoda datové sady.

> [!NOTE]
>  Po potvrzení změn do datové sady nebo data tabulky (voláním <xref:System.Data.DataSet.AcceptChanges%2A> metoda), `GetChanges` metoda nevrátí žádná data. Pokud aplikace potřebuje ke zpracování změněných řádků, je nutné zpracovat změny před voláním `AcceptChanges` metoda.

Volání <xref:System.Data.DataSet.GetChanges%2A> metoda datové sady nebo data tabulky vrátí novou sadu dat nebo dat tabulku, která obsahuje pouze záznamy, které se změnily. Pokud chcete získat konkrétních záznamů – například pouze nové záznamy nebo pouze změněné záznamy – můžete předat hodnotu z <xref:System.Data.DataRowState> výčet jako parametr, který se `GetChanges` metoda.

Použití <xref:System.Data.DataRowVersion> výčtu pro přístup k různé verze řádku (například původní hodnoty, které byly v řádku před jeho zpracování).

#### <a name="to-get-all-changed-records-from-a-dataset"></a>Chcete-li získat všechny změněné záznamy z datové sady

-   Volání <xref:System.Data.DataSet.GetChanges%2A> metoda datové sady.

     Následující příklad vytvoří novou datovou sadu s názvem `changedRecords` a naplní se všechny změněné záznamy z jiné datovou sadu s názvem `dataSet1`.

     [!code-csharp[VbRaddataEditing#14](../data-tools/codesnippet/CSharp/validate-data-in-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#14](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_2.vb)]

#### <a name="to-get-all-changed-records-from-a-data-table"></a>Chcete-li získat všechny změněné záznamy z tabulky dat

-   Volání <xref:System.Data.DataTable.GetChanges%2A> metoda DataTable.

     Následující příklad vytvoří novou tabulku dat volat `changedRecordsTable` a naplní se všechny změněné záznamy z jiné tabulky dat volat `dataTable1`.

     [!code-csharp[VbRaddataEditing#15](../data-tools/codesnippet/CSharp/validate-data-in-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#15](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_3.vb)]

#### <a name="to-get-all-records-that-have-a-specific-row-state"></a>Chcete-li získat všechny záznamy, které mají stav specifickým řádkem

-   Volání `GetChanges` metodu datovou sadu nebo tabulku dat a předejte jí <xref:System.Data.DataRowState> hodnota výčtu jako argument.

     Následující příklad ukazuje, jak vytvořit novou datovou sadu s názvem `addedRecords` a jeho naplnění pouze záznamy, které byly přidány do `dataSet1` datovou sadu.

     [!code-csharp[VbRaddataEditing#16](../data-tools/codesnippet/CSharp/validate-data-in-datasets_4.cs)]
     [!code-vb[VbRaddataEditing#16](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_4.vb)]

     Následující příklad ukazuje, jak chcete zobrazit všechny záznamy, které byly nedávno přidané do `Customers` tabulky:

     [!code-csharp[VbRaddataEditing#17](../data-tools/codesnippet/CSharp/validate-data-in-datasets_5.cs)]
     [!code-vb[VbRaddataEditing#17](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_5.vb)]

## <a name="access-the-original-version-of-a-datarow"></a>Přístup k původní verzi DataRow
Provedení změn na řádky dat, datová sada zachovává původní (<xref:System.Data.DataRowVersion.Original>) a new (<xref:System.Data.DataRowVersion.Current>) verze řádku. Například před volání `AcceptChanges` metoda, vaše aplikace mohou přistupovat k různé verze záznamu (podle definice v <xref:System.Data.DataRowVersion> – výčet) a odpovídajícím způsobem zpracovat změny.

> [!NOTE]
>  Existují různé verze řádku až poté, co bylo upraveno a před ním `AcceptChanges` byla volána metoda. Po `AcceptChanges` byla volána metoda, aktuální a původní verze jsou stejné.

Předávání <xref:System.Data.DataRowVersion> hodnotu společně s index sloupce (nebo název sloupce jako řetězec) vrací hodnotu z verze konkrétního řádku tohoto sloupce. Změněné sloupec se identifikuje během <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.ColumnChanged> události. Toto je vhodná doba Kontrola verze jiný řádek pro účely ověření. Pokud máte dočasně pozastaveno omezení, tyto události nebudou vyvolávat a budete muset prostřednictvím kódu programu Identifikujte však sloupce, které se změnily. Můžete to provést pomocí iterace <xref:System.Data.DataTable.Columns%2A> shromažďování a porovnávání různými <xref:System.Data.DataRowVersion> hodnoty.

#### <a name="to-get-the-original-version-of-a-record"></a>Chcete-li získat původní verzi záznam

-   Přístup k hodnotě sloupce předáním v <xref:System.Data.DataRowVersion> řádku, které chcete vrátit.

     Následující příklad ukazuje, jak používat <xref:System.Data.DataRowVersion> hodnotu získat původní hodnotu `CompanyName` pole <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#21](../data-tools/codesnippet/CSharp/validate-data-in-datasets_6.cs)]
     [!code-vb[VbRaddataEditing#21](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_6.vb)]

## <a name="access-the-current-version-of-a-datarow"></a>Přístup k aktuální verzi DataRow

#### <a name="to-get-the-current-version-of-a-record"></a>Chcete-li získat aktuální záznam verze

-   Přístup k hodnotě sloupce a poté přidejte parametr do indexu, která určuje, která verze řádku, které chcete vrátit.

     Následující příklad ukazuje, jak používat <xref:System.Data.DataRowVersion> hodnota, která má získat aktuální hodnotu `CompanyName` pole <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#22](../data-tools/codesnippet/CSharp/validate-data-in-datasets_7.cs)]
     [!code-vb[VbRaddataEditing#22](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_7.vb)]

## <a name="see-also"></a>Viz také

- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Postupy: Ověřování dat v ovládacím prvku Windows Forms DataGridView](/dotnet/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control)
- [Postupy: Zobrazení ikon chyb pro ověřování formuláře pomocí komponenty Windows Forms ErrorProvider](/dotnet/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider)