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
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 80f258e87bd7bd197460d5ff9ab29b6964347f7c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925418"
---
# <a name="validate-data-in-datasets"></a>Ověřování dat v datových sadách
Ověřování dat je proces potvrzení, že hodnoty, které jsou zadány do datových objektů, jsou v souladu s omezeními v rámci schématu datové sady. Proces ověřování také potvrdí, že tyto hodnoty následují pravidla, která byla pro vaši aplikaci vytvořena. Před odesláním aktualizací do podkladové databáze je dobrým zvykem ověřit data. Tím se snižuje počet chyb a také potenciální počet odezvy mezi aplikací a databází.

Můžete potvrdit, že data, která jsou zapsána do datové sady, jsou platná sestavením kontrol ověření do samotné datové sady. Datová sada může kontrolovat data bez ohledu na to, jak je prováděna aktualizace – ať už přímo ovládacími prvky ve formuláři, v rámci součásti nebo jiným způsobem. Vzhledem k tomu, že datová sada je součástí vaší aplikace (na rozdíl od back-endu databáze), je logické místo pro sestavení ověřování specifického pro aplikaci.

Nejlepším místem pro přidání ověřování do aplikace je soubor částečné třídy datové sady. V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]otevřete **Návrhář datových sad** a dvakrát klikněte na sloupec nebo tabulku, pro které chcete vytvořit ověření. Tato akce automaticky vytvoří <xref:System.Data.DataTable.ColumnChanging> obslužnou rutinu události nebo. <xref:System.Data.DataTable.RowChanging>

## <a name="validate-data"></a>Ověřit data
Ověřování v rámci datové sady je provedeno následujícími způsoby:

- Vytvořením vlastního ověřování specifického pro aplikaci, které během změn může kontrolovat hodnoty v jednotlivých datových sloupcích. Další informace najdete v tématu [jak: Ověří data během změny](validate-data-in-datasets.md)sloupce.

- Vytvořením vlastního ověřování specifického pro aplikaci, které může kontrolovat data na hodnoty v průběhu změny celého řádku dat. Další informace najdete v tématu [jak: Ověří data při změnách](validate-data-in-datasets.md)řádku.

- Vytvořením klíčů, jedinečných omezení a tak dále jako součást skutečné definice schématu pro datovou sadu.

- Nastavením vlastností <xref:System.Data.DataColumn> objektu, <xref:System.Data.DataColumn.MaxLength%2A>například <xref:System.Data.DataColumn.AllowDBNull%2A>, a <xref:System.Data.DataColumn.Unique%2A>.

Několik událostí je vyvoláno <xref:System.Data.DataTable> objektem, když dojde ke změně v záznamu:

- Události <xref:System.Data.DataTable.ColumnChanging> a<xref:System.Data.DataTable.ColumnChanged> jsou vyvolány během a po každé změně do jednotlivého sloupce. <xref:System.Data.DataTable.ColumnChanging> Událost je užitečná v případě, že chcete ověřit změny v konkrétních sloupcích. Informace o navrhované změně jsou předány jako argument s událostí.
- Události <xref:System.Data.DataTable.RowChanging> a<xref:System.Data.DataTable.RowChanged> jsou vyvolány během každé změny řádku a po ní. <xref:System.Data.DataTable.RowChanging> Událost je obecnější. Indikuje, že se na řádku vyskytuje změna, ale nevíte, který sloupec se změnil.

Ve výchozím nastavení každá změna ve sloupci proto vyvolává čtyři události. První je <xref:System.Data.DataTable.ColumnChanging> události a <xref:System.Data.DataTable.ColumnChanged> pro konkrétní sloupec, který se mění. Další jsou <xref:System.Data.DataTable.RowChanging> události a <xref:System.Data.DataTable.RowChanged> . Je-li na řádku provedeno více změn, události budou vyvolány pro každou změnu.

> [!NOTE]
> <xref:System.Data.DataRow.BeginEdit%2A> Metoda datového řádku vypne <xref:System.Data.DataTable.RowChanging> události a <xref:System.Data.DataTable.RowChanged> po změně každého jednotlivého sloupce. V takovém případě událost není vyvolána, <xref:System.Data.DataRow.EndEdit%2A> <xref:System.Data.DataTable.RowChanging> dokud není volána metoda a události a <xref:System.Data.DataTable.RowChanged> jsou vyvolány pouze jednou. Další informace najdete v tématu vypnutí [omezení při naplňování datové sady](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

Událost, kterou zvolíte, závisí na tom, jak podrobně chcete ověřování provést. Pokud je důležité zachytit chybu okamžitě při změně sloupce, sestavte ověření pomocí <xref:System.Data.DataTable.ColumnChanging> události. V opačném případě <xref:System.Data.DataTable.RowChanging> použijte událost, která by mohla vést k zachycení několika chyb najednou. Pokud jsou vaše data strukturována tak, aby byla hodnota jednoho sloupce ověřena na základě obsahu jiného sloupce, proveďte ověření během <xref:System.Data.DataTable.RowChanging> události.

Po aktualizaci <xref:System.Data.DataTable> záznamů objekt vyvolá události, na které můžete reagovat, když dojde ke změnám a po provedení změn.

Pokud vaše aplikace používá typovou datovou sadu, můžete vytvořit obslužné rutiny událostí silného typu. Tím přidáte čtyři další události typu, pro které můžete vytvořit obslužné rutiny `dataTableNameRowChanged`: `dataTableNameRowDeleting` `dataTableNameRowChanging`,, `dataTableNameRowDeleted`a. Tyto obslužné rutiny událostí typu předávají argument, který obsahuje názvy sloupců tabulky, které usnadňují zápis a čtení kódu.

## <a name="data-update-events"></a>Události aktualizace dat

|Událost|Popis|
|-----------|-----------------|
|<xref:System.Data.DataTable.ColumnChanging>|Změní se hodnota ve sloupci. Událost předá do sebe řádek a sloupec, spolu s navrhovanou novou hodnotou.|
|<xref:System.Data.DataTable.ColumnChanged>|Hodnota ve sloupci byla změněna. Událost předá do sebe řádek a sloupec, společně s navrhovanou hodnotou.|
|<xref:System.Data.DataTable.RowChanging>|Změny provedené u <xref:System.Data.DataRow> objektu se budou zasílat zpátky do datové sady. Pokud jste nevolali <xref:System.Data.DataRow.BeginEdit%2A> metodu <xref:System.Data.DataTable.RowChanging> , událost je vyvolána pro každou změnu sloupce ihned po <xref:System.Data.DataTable.ColumnChanging> vyvolání události. Pokud jste volali <xref:System.Data.DataRow.BeginEdit%2A> před provedením změn <xref:System.Data.DataTable.RowChanging> , událost je vyvolána <xref:System.Data.DataRow.EndEdit%2A> pouze při volání metody.<br /><br /> Událost předá řádek, spolu s hodnotou, která označuje, jaký typ akce (změny, vložení a tak dále) se provádí.|
|<xref:System.Data.DataTable.RowChanged>|Řádek byl změněn. Událost předá řádek, spolu s hodnotou, která označuje, jaký typ akce (změny, vložení a tak dále) se provádí.|
|<xref:System.Data.DataTable.RowDeleting>|Odstraňuje se řádek. Událost předá tento řádek spolu s hodnotou, která označuje, jaký typ akce (odstranění) se provádí.|
|<xref:System.Data.DataTable.RowDeleted>|Řádek byl odstraněn. Událost předá tento řádek spolu s hodnotou, která označuje, jaký typ akce (odstranění) se provádí.|

Události <xref:System.Data.DataTable.ColumnChanging>, <xref:System.Data.DataTable.RowChanging> a<xref:System.Data.DataTable.RowDeleting> jsou vyvolány během procesu aktualizace. Tyto události můžete použít k ověření dat nebo provádění jiných typů zpracování. Vzhledem k tomu, že aktualizace probíhá během těchto událostí, můžete ji zrušit vyvoláním výjimky, která zabrání dokončení aktualizace.

<xref:System.Data.DataTable.ColumnChanged> Události<xref:System.Data.DataTable.RowChanged> a jsou<xref:System.Data.DataTable.RowDeleted> události oznámení, které jsou vyvolány po úspěšném dokončení aktualizace. Tyto události jsou užitečné, když chcete provést další akci na základě úspěšné aktualizace.

## <a name="validate-data-during-column-changes"></a>Ověřit data během změny sloupce

> [!NOTE]
> **Návrhář datových sad** vytvoří částečnou třídu, ve které lze ověřovací logiku přidat do datové sady. Datová sada generovaná návrhářem neodstraní ani nezmění žádný kód v dílčí třídě.

Data můžete ověřit při změně hodnoty v datovém sloupci tím, že odpovíte na <xref:System.Data.DataTable.ColumnChanging> událost. Při vyvolání Tato událost předává argument události (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>), který obsahuje hodnotu, která je navržena pro aktuální sloupec. Na základě obsahu `e.ProposedValue`můžete:

- Přijměte navrhovanou hodnotu tím, že nic nedělá.

- Odmítne navrhovanou hodnotu nastavením chyby sloupce (<xref:System.Data.DataRow.SetColumnError%2A>) z obslužné rutiny události měnící sloupce.

- Volitelně můžete pomocí <xref:System.Windows.Forms.ErrorProvider> ovládacího prvku zobrazit uživateli chybovou zprávu. Další informace najdete v tématu [Komponenta ErrorProvider](/dotnet/framework/winforms/controls/errorprovider-component-windows-forms).

Ověřování lze také provést během <xref:System.Data.DataTable.RowChanging> události.

## <a name="validate-data-during-row-changes"></a>Ověřit data během změny řádku
Můžete napsat kód pro ověření, že každý sloupec, který chcete ověřit, obsahuje data, která splňují požadavky vaší aplikace. Provedete to tak, že nastavíte sloupec tak, aby označoval, že obsahuje chybu, pokud navrhovaná hodnota nesouhlasí. Následující příklady nastavují chybu sloupce, pokud `Quantity` je sloupec 0 nebo menší. Obslužné rutiny události měnící řádky by měly vypadat podobně jako v následujících příkladech.

### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>Ověření dat při změně řádku (Visual Basic)

1. Otevřete svou datovou sadu v **Návrhář Dataset**. Další informace najdete v tématu [Návod: Vytvoření datové sady v Návrhář datových sad](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2. Dvakrát klikněte na záhlaví tabulky, kterou chcete ověřit. Tato akce automaticky vytvoří <xref:System.Data.DataTable.RowChanging> obslužnou rutinu <xref:System.Data.DataTable> události v souboru částečné třídy datové sady.

    > [!TIP]
    > Dvojitým kliknutím nalevo od názvu tabulky vytvoříte obslužnou rutinu události měnící řádek. Pokud dvakrát kliknete na název tabulky, můžete ho upravit.

     [!code-vb[VbRaddataValidating#3](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_1.vb)]

### <a name="to-validate-data-when-a-row-changes-c"></a>Ověření dat při změně řádku (C#)

1. Otevřete svou datovou sadu v **Návrhář Dataset**. Další informace najdete v tématu [Návod: Vytvoření datové sady v Návrhář datových sad](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2. Dvakrát klikněte na záhlaví tabulky, kterou chcete ověřit. Tato akce vytvoří soubor částečné třídy pro <xref:System.Data.DataTable>.

    > [!NOTE]
    > **Návrhář datových sad** nevytváří automaticky obslužnou rutinu události pro <xref:System.Data.DataTable.RowChanging> událost. Je nutné vytvořit metodu pro zpracování <xref:System.Data.DataTable.RowChanging> události a spustit kód pro zapojení události do inicializační metody tabulky.

3. Zkopírujte následující kód do částečné třídy:

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

## <a name="to-retrieve-changed-rows"></a>Načtení změněných řádků
Každý řádek v tabulce dat má <xref:System.Data.DataRow.RowState%2A> vlastnost, která sleduje aktuální stav tohoto řádku pomocí hodnot <xref:System.Data.DataRowState> ve výčtu. Můžete vrátit změněné řádky z datové sady nebo tabulky dat voláním `GetChanges` metody <xref:System.Data.DataSet> nebo <xref:System.Data.DataTable>. Můžete ověřit, zda existují změny před voláním `GetChanges` <xref:System.Data.DataSet.HasChanges%2A> voláním metody datové sady.

> [!NOTE]
> Po potvrzení změn v datové sadě nebo tabulce dat (voláním <xref:System.Data.DataSet.AcceptChanges%2A> metody) `GetChanges` nevrátí metoda žádná data. Pokud vaše aplikace potřebuje zpracovat změněné řádky, je nutné před voláním `AcceptChanges` metody zpracovat změny.

<xref:System.Data.DataSet.GetChanges%2A> Volání metody datové sady nebo tabulky dat vrátí novou datovou sadu nebo datovou tabulku, která obsahuje pouze záznamy, které byly změněny. Pokud chcete získat konkrétní záznamy, například pouze nové záznamy nebo pouze změněné záznamy, můžete předat hodnotu z <xref:System.Data.DataRowState> výčtu jako parametr `GetChanges` metodě.

<xref:System.Data.DataRowVersion> Použijte výčet pro přístup k různým verzím řádku (například původní hodnoty, které byly v řádku před jeho zpracováním).

### <a name="to-get-all-changed-records-from-a-dataset"></a>Získání všech změněných záznamů z datové sady

- <xref:System.Data.DataSet.GetChanges%2A> Zavolejte metodu datové sady.

     Následující příklad vytvoří novou datovou sadu s `changedRecords` názvem a naplní ji všemi změněnými záznamy z jiné datové sady `dataSet1`s názvem.

     [!code-csharp[VbRaddataEditing#14](../data-tools/codesnippet/CSharp/validate-data-in-datasets_2.cs)]
     [!code-vb[VbRaddataEditing#14](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_2.vb)]

### <a name="to-get-all-changed-records-from-a-data-table"></a>Získání všech změněných záznamů z tabulky dat

- <xref:System.Data.DataTable.GetChanges%2A> Zavolejte metodu objektu DataTable.

     Následující příklad vytvoří novou tabulku dat s názvem `changedRecordsTable` a naplní ji všemi změněnými záznamy z jiné tabulky dat s názvem. `dataTable1`

     [!code-csharp[VbRaddataEditing#15](../data-tools/codesnippet/CSharp/validate-data-in-datasets_3.cs)]
     [!code-vb[VbRaddataEditing#15](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_3.vb)]

### <a name="to-get-all-records-that-have-a-specific-row-state"></a>Získání všech záznamů, které mají určitý stav řádku

- Zavolejte metodu datové sady nebo tabulky dat a <xref:System.Data.DataRowState> předejte hodnotu výčtu jako argument. `GetChanges`

     Následující příklad ukazuje, jak vytvořit novou datovou sadu s `addedRecords` názvem a naplnit ji pouze záznamy, které byly přidány `dataSet1` do datové sady.

     [!code-csharp[VbRaddataEditing#16](../data-tools/codesnippet/CSharp/validate-data-in-datasets_4.cs)]
     [!code-vb[VbRaddataEditing#16](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_4.vb)]

     Následující příklad ukazuje, jak vrátit všechny záznamy, které byly nedávno přidány do `Customers` tabulky:

     [!code-csharp[VbRaddataEditing#17](../data-tools/codesnippet/CSharp/validate-data-in-datasets_5.cs)]
     [!code-vb[VbRaddataEditing#17](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_5.vb)]

## <a name="access-the-original-version-of-a-datarow"></a>Přístup k původní verzi objektu DataRow
Pokud jsou provedeny změny v řádcích dat, datová sada si uchová původní (<xref:System.Data.DataRowVersion.Original>) a nové (<xref:System.Data.DataRowVersion.Current>) verze řádku. Například před voláním `AcceptChanges` metody může vaše aplikace přistupovat k různým verzím záznamu (jak je definováno <xref:System.Data.DataRowVersion> ve výčtu) a odpovídajícím způsobem zpracovat změny.

> [!NOTE]
> Různé verze řádku existují až po úpravě a před `AcceptChanges` voláním metody. Po volání `AcceptChanges` metody jsou aktuální a původní verze stejné.

<xref:System.Data.DataRowVersion> Předání hodnoty spolu s indexem sloupce (nebo názvem sloupce jako řetězce) vrátí hodnotu z verze konkrétního řádku daného sloupce. Změněný sloupec se identifikuje během <xref:System.Data.DataTable.ColumnChanging> událostí a. <xref:System.Data.DataTable.ColumnChanged> To je dobrý čas pro kontrolu různých verzí řádků pro účely ověření. Pokud jste však dočasně pozastavili omezení, tyto události nebudou vyvolány a budete muset programově určit, které sloupce se změnily. To můžete provést tak, že provedete iteraci <xref:System.Data.DataTable.Columns%2A> kolekce a porovnáváte různé <xref:System.Data.DataRowVersion> hodnoty.

### <a name="to-get-the-original-version-of-a-record"></a>Získání původní verze záznamu

- Přejděte k hodnotě sloupce předáním na <xref:System.Data.DataRowVersion> řádku, který chcete vrátit.

     Následující příklad ukazuje, jak použít <xref:System.Data.DataRowVersion> hodnotu k získání původní hodnoty `CompanyName` pole v <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#21](../data-tools/codesnippet/CSharp/validate-data-in-datasets_6.cs)]
     [!code-vb[VbRaddataEditing#21](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_6.vb)]

## <a name="access-the-current-version-of-a-datarow"></a>Přístup k aktuální verzi objektu DataRow

### <a name="to-get-the-current-version-of-a-record"></a>Získání aktuální verze záznamu

- Přistoupit k hodnotě sloupce a poté přidejte parametr do indexu, který označuje, která verze řádku má být vrácena.

     Následující příklad ukazuje, jak použít <xref:System.Data.DataRowVersion> hodnotu k získání aktuální hodnoty `CompanyName` pole v <xref:System.Data.DataRow>:

     [!code-csharp[VbRaddataEditing#22](../data-tools/codesnippet/CSharp/validate-data-in-datasets_7.cs)]
     [!code-vb[VbRaddataEditing#22](../data-tools/codesnippet/VisualBasic/validate-data-in-datasets_7.vb)]

## <a name="see-also"></a>Viz také:

- [Nástroje datových sad v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Postupy: Ověřit data v ovládacím prvku DataGridView model Windows Forms](/dotnet/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control)
- [Postupy: Zobrazit chybové ikony pro ověření formuláře pomocí součásti model Windows Forms ErrorProvider](/dotnet/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider)