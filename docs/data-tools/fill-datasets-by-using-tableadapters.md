---
title: Vyplnění datové sady s použitím objektů TableAdapters
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- datasets [Visual Basic]
- datasets [Visual Basic], loading data
- data retrieval
- retrieving data
- datasets [Visual Basic], filling
- data [Visual Studio], retrieving
- data [Visual Studio], datasets
ms.assetid: 55f3bfbe-db78-4486-add3-c62f49e6b9a0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 57387cecfdf58667998cc3766617d37c62e0f4ab
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757078"
---
# <a name="fill-datasets-by-using-tableadapters"></a>Vyplnění datové sady s použitím objektů TableAdapters

Součást TableAdapter doplní datové sady daty z databáze, na základě jednoho nebo více dotazy nebo uložené procedury, které zadáte. Můžete také provést TableAdapters přidání, aktualizace a odstranění v databázi k zachování změn, které můžete provést na datovou sadu. Mohou také vystavovat globální příkazy, které se nevztahují žádné konkrétní tabulky.

> [!NOTE]
> TableAdapters generované návrháři Visual Studio. Pokud vytvoříte datové sady prostřednictvím kódu programu, použijte DataAdapter, který je třída rozhraní .NET Framework.

Podrobné informace o operacích TableAdapter můžete přejít přímo na jednu z těchto témat:

|Téma|Popis|
|-----------|-----------------|
|[Vytvoření a konfigurace objektů TableAdapter](../data-tools/create-and-configure-tableadapters.md)|Jak používat návrháři k vytvoření a konfigurace TableAdapters|
|[Vytvoření parametrizovaných dotazů TableAdapter](../data-tools/create-parameterized-tableadapter-queries.md)|Postup povolení uživatelům zadat argumenty procedury TableAdapter nebo dotazy|
|[Přímý přístup k databázi pomocí objektů TableAdapter](../data-tools/directly-access-the-database-with-a-tableadapter.md)|Jak používat metody Dbdirect TableAdapters|
|[Vypnutí omezení při naplňování datové sady](../data-tools/turn-off-constraints-while-filling-a-dataset.md)|Jak pracovat s omezení cizího klíče při aktualizaci dat|
|[Postup rozšíření funkcí TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)|Postup přidání vlastního kódu do prvků TableAdapters|
|[Čtení dat XML do datové sady](../data-tools/read-xml-data-into-a-dataset.md)|Jak pracovat s XML|

<a name="tableadapter-overview"></a>

## <a name="tableadapter-overview"></a>TableAdapter – přehled

TableAdapters jsou generované Návrhář součásti, které se připojují k databázi, spusťte dotazy nebo uložené procedury a vyplníte jejich DataTable vrácená data. TableAdapters také odeslat aktualizovaná data z vaší aplikace zpět do databáze. Můžete spustit jako v mnoha dotazy tak, jak chcete na TableAdapter tak dlouho, dokud schématu tabulky, ke kterému je přiřazeno TableAdapter vracejí data, která vyhovuje. Následující diagram znázorňuje, jak TableAdapters komunikovat s databází a dalších objektů v paměti:

![Tok dat v aplikaci klienta](../data-tools/media/clientdatadiagram.gif)

Během TableAdapters jsou navrženy s **návrháře Dataset**, jako vnořené třídy nejsou generované třídy TableAdapter <xref:System.Data.DataSet>. Se nacházejí v samostatné obory názvů, které jsou specifické pro každé datové sady. Například, pokud máte datovou sadu s názvem `NorthwindDataSet`, TableAdapters, které jsou přidružené <xref:System.Data.DataTable>s v `NorthwindDataSet` by v `NorthwindDataSetTableAdapters` oboru názvů. Pro programový přístup k určitému typu TableAdapter musíte deklarovat novou instanci typu TableAdapter. Příklad:

[!code-csharp[VbRaddataTableAdapters#7](../data-tools/codesnippet/CSharp/fill-datasets-by-using-tableadapters_1.cs)]
[!code-vb[VbRaddataTableAdapters#7](../data-tools/codesnippet/VisualBasic/fill-datasets-by-using-tableadapters_1.vb)]

## <a name="associated-datatable-schema"></a>Přidružené schéma DataTable

Pokud vytvoříte TableAdapter, použijte počátečního dotazu nebo uložené procedury k definování schématu TableAdapter přidruženému <xref:System.Data.DataTable>. Spuštění tohoto počáteční dotazu nebo uložené procedury voláním TableAdapter `Fill` – metoda (který vyplní celé TableAdapter přidruženému <xref:System.Data.DataTable>). Všechny změny provedené TableAdapter hlavní dotazu se projeví ve schématu tabulky přidružená data. Například odebrání sloupce z hlavní dotazu také odebere sloupec v tabulce přidružená data. Pokud žádné další dotazy na TableAdapter používat příkazy SQL, které vracejí sloupce, které nejsou v hlavní dotazu, Návrhář pokusí synchronizovat změny sloupce mezi hlavní dotaz a další dotazy.

## <a name="tableadapter-update-commands"></a>Příkazy aktualizace TableAdapter

Aktualizace funkcí TableAdapter je závislý na to, kolik informací je k dispozici v hlavní dotaz **Průvodce nastavením TableAdapter**. Například TableAdapters, které jsou nakonfigurované k načtení hodnoty z více tabulek (pomocí `JOIN`), skalárních hodnot, zobrazení nebo výsledky agregační funkce nejsou vytvořeny původně s možností odesílání aktualizací zpět na základní databázi. Ale můžete nakonfigurovat `INSERT`, `UPDATE`, a `DELETE` ručně v příkazy **vlastnosti** okno.

## <a name="tableadapter-queries"></a>TableAdapter – dotazy

![TableAdapter s více dotazy](../data-tools/media/tableadapter.gif)

TableAdapters může obsahovat více dotazů k vyplnění tabulky jejich přidružená data. Objektu TableAdapter lze definovat tolik dotazů, kolik vyžaduje vaše aplikace, pokud každý dotaz vrací data, která odpovídají stejnému schématu jako jeho přidružená tabulka dat. Tato funkce umožňuje TableAdapter načíst odlišné výsledky na základě kritérií odlišné.

Například pokud vaše aplikace obsahuje tabulku s názvy zákazníka, můžete vytvořit dotaz, který vyplní celé tabulky s každou jméno zákazníka, který začíná písmenem určité a druhý, vyplní celé tabulky s všem zákazníkům, kteří se nacházejí ve stejné stavu. K vyplnění `Customers` tabulky se zákazníky daný stav, můžete vytvořit `FillByState` dotaz, který přebírá parametr pro hodnotu stavu následujícím způsobem: `SELECT * FROM Customers WHERE State = @State`. Spusťte dotaz voláním `FillByState` metoda a předávání hodnotu parametru, jako to: `CustomerTableAdapter.FillByState("WA")`.

Kromě přidání dotazů, které vrátí data jako tabulku dat TableAdapter stejné schéma, můžete přidat dotazů, které vrátí skalárních hodnot (jednu). Například dotaz, který vrací počet zákazníků (`SELECT Count(*) From Customers`) je platná pro `CustomersTableAdapter,` to i v případě, že data, která je vrácena neodpovídají schématu v tabulce.

## <a name="clearbeforefill-property"></a>Vlastnost ClearBeforeFill

Ve výchozím nastavení můžete při každém spuštění dotazu k vyplnění tabulky dat TableAdapter stávající data není zaškrtnuta, a jenom výsledky dotazu jsou načtena do tabulky. Nastavte TableAdapter `ClearBeforeFill` vlastnost `false` Pokud chcete přidat nebo sloučení data, která je na existující data v tabulce data vrácená z dotazu. Bez ohledu na to, jestli vymazat data budete muset explicitně odeslání aktualizací zpět do databáze, pokud chcete, aby je uchoval. Proto nezapomeňte uložit změny dat v tabulce před spuštěním další dotaz, který vyplní celé tabulky. Další informace najdete v tématu [aktualizace dat pomocí TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md).

## <a name="tableadapter-inheritance"></a>Dědičnost TableAdapter

TableAdapters rozšířit funkci adaptérů standardní dat zapouzdřením nakonfigurované <xref:System.Data.Common.DataAdapter> třídy. Ve výchozím nastavení, TableAdapter dědí z <xref:System.ComponentModel.Component> třídy a nelze přetypovat <xref:System.Data.Common.DataAdapter> třídy. Přetypování TableAdapter k <xref:System.Data.Common.DataAdapter> třídy má za následek <xref:System.InvalidCastException> chyby. Chcete-li změnit základní třídu TableAdapter, můžete zadat třídu odvozenou z <xref:System.ComponentModel.Component> v **základní třída** vlastnost TableAdapter v **návrháře Dataset**.

## <a name="tableadapter-methods-and-properties"></a>TableAdapter metod a vlastností

Třída TableAdapter není součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. To znamená, že jste nelze vyhledat ho v dokumentaci nebo **Prohlížeč objektů**. Je vytvořen v době návrhu při použití některého z průvodců již bylo zmíněno dříve. Název tabulky, které pracujete s vychází název, který je přiřazený k TableAdapter při jeho vytvoření. Například při vytváření TableAdapter podle tabulky v databázi s názvem `Orders`, TableAdapter jmenuje `OrdersTableAdapter`. Název třídy TableAdapter lze změnit pomocí **název** vlastnost **návrháře Dataset**.

Tady jsou běžně používané metody a vlastnosti TableAdapters:

|Člen|Popis|
|------------|-----------------|
|`TableAdapter.Fill`|Naplní tabulku přidružená data TableAdapter s výsledky TableAdapter `SELECT` příkaz.|
|`TableAdapter.Update`|Posílá změny zpět do databáze a vrátí celé číslo představující počet řádků, vliv na aktualizace. Další informace najdete v tématu [aktualizace dat pomocí TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md).|
|`TableAdapter.GetData`|Vrátí novou <xref:System.Data.DataTable> , naplní se data.|
|`TableAdapter.Insert`|Vytvoří v tabulce dat nový řádek. Další informace najdete v tématu [vkládání nových záznamů do databáze](../data-tools/insert-new-records-into-a-database.md).|
|`TableAdapter.ClearBeforeFill`|Určuje, zda bude tabulka dat před voláním metody `Fill` vyprázdněna.|

## <a name="tableadapter-update-method"></a>Metoda aktualizace TableAdapter

Objekty TableAdapter používají příkazy pro čtení a zápis dat z databáze. Použít TableAdapter počáteční `Fill` (hlavní) dotazu jako základ pro vytváření schéma tabulky přidružená data, a taky `InsertCommand`, `UpdateCommand`, a `DeleteCommand` příkazy, které jsou přidružené `TableAdapter.Update` metoda. Volání metody TableAdapter `Update` metoda se spouští příkazy, které byly vytvořeny, když byl původně nakonfigurovaný TableAdapter, není jednou z další dotazy, které jste přidali pomocí **Průvodce konfigurací dotazu TableAdapter**.

Při použití TableAdapter efektivně provádí stejné operace s příkazy, které by obvykle provedl. Například při volání adaptéru `Fill` metody adaptér spouští příkaz data jeho `SelectCommand` vlastnost a používá čtecí modul dat (například <xref:System.Data.SqlClient.SqlDataReader>) načíst do tabulky data sadu výsledků dotazu. Podobně při volání adaptéru `Update` metoda, běží příslušný příkaz (v `UpdateCommand`, `InsertCommand`, a `DeleteCommand` vlastnosti) pro každý změnit záznam v tabulce data.

> [!NOTE]
> Pokud je dostatek informací v hlavní dotazu `InsertCommand`, `UpdateCommand`, a `DeleteCommand` příkazy, které se vytvořily ve výchozím nastavení při se generuje TableAdapter. Pokud je TableAdapter hlavní dotaz je více než jedné tabulce `SELECT` příkaz, je možné, nebudou moci generovat návrháře `InsertCommand`, `UpdateCommand`, a `DeleteCommand`. Pokud tyto příkazy nejsou generované, může dojít chybě při spuštění `TableAdapter.Update` metoda.

## <a name="tableadapter-generatedbdirectmethods"></a>Vlastnost GenerateDBDirectMethods třídy TableAdapter

Kromě `InsertCommand`, `UpdateCommand`, a `DeleteCommand`, TableAdapters jsou vytvořeny pomocí metody, které můžete spustit přímo v databázi. Můžete volat tyto metody (`TableAdapter.Insert`, `TableAdapter.Update`, a `TableAdapter.Delete`) přímo k manipulaci s daty v databázi. To znamená, že tyto jednotlivé metody můžete volat z kódu namísto volání `TableAdapter.Update` pro zpracování vložení, aktualizace a odstranění, které čekají na vyřízení pro tabulku přidružená data.

Pokud nechcete vytvořit tyto přímé metody, nastavte TableAdapter **generatedbdirectmethods –** vlastnost `false` (v **vlastnosti** okno). Další dotazy, které jsou přidány do TableAdapter jsou samostatné dotazy – jejich negenerovat zprávy o těchto metod.

## <a name="tableadapter-support-for-nullable-types"></a>TableAdapter podporu pro typy s možnou hodnotou Null

TableAdapters podporují typy s možnou hodnotou Null `Nullable(Of T)` a `T?`. Další informace o typech s povolenou hodnotou Null v jazyce Visual Basic najdete v tématu [typy s možnou hodnotou Null hodnot](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types). Další informace o typech s povolenou hodnotou Null v jazyce C#, najdete v části [používat typy s možnou hodnotou Null](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types).

<a name="tableadaptermanager-reference"></a>

## <a name="tableadaptermanager-reference"></a>TableAdapterManager odkaz

Ve výchozím nastavení vygeneruje třídu TableAdapterManager při vytváření datovou sadu, která obsahuje související tabulky. Abyste zabránili generovaná třída, změňte hodnotu `Hierarchical Update` vlastnosti datové sady na hodnotu false. Při přetažení tabulku, která má vztah na návrhovou plochu formuláře Windows nebo WPF stránky, Visual Studio deklaruje členské proměnné třídy. Pokud nepoužijete vazby dat, budete muset ručně deklarovat proměnnou.

Třída TableAdapterManager není součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Proto je nelze jej vyhledat v dokumentaci. Je vytvořen v době návrhu jako součást procesu vytváření datové sady.

Toto jsou často používané metody a vlastnosti `TableAdapterManager` třídy:

|Člen|Popis|
|------------|-----------------|
|`UpdateAll` – Metoda|Uloží všechna data ze všech tabulek, data.|
|`BackUpDataSetBeforeUpdate` Vlastnost|Určuje, jestli se mají vytvořit si záložní kopii datovou sadu před spuštěním `TableAdapterManager.UpdateAll` metoda. Logická hodnota.|
|*Název tabulky* `TableAdapter` vlastnost|Představuje TableAdapter. Vygenerovaný TableAdapterManager obsahuje vlastnost pro každý `TableAdapter` spravuje. Například datové sady s tabulkou Zákazníci a objednávky vygeneruje s TableAdapterManager, který obsahuje `CustomersTableAdapter` a `OrdersTableAdapter` vlastnosti.|
|`UpdateOrder` Vlastnost|Určuje pořadí jednotlivých insert, update a delete příkazy. Tuto možnost nastavíte na jednu z hodnot v `TableAdapterManager.UpdateOrderOption` výčtu.<br /><br /> Ve výchozím nastavení `UpdateOrder` je nastaven na **InsertUpdateDelete**. To znamená, které vloží, pak aktualizací a poté se odstraní se pro všechny tabulky v datové sadě.|

## <a name="security"></a>Zabezpečení

Při použití datové příkazy s vlastnost CommandType nastavena na <xref:System.Data.CommandType.Text>, pečlivě zkontrolujte informace, které se odesílá z klienta před jeho odesláním k vaší databázi. Uživatelé se zlými úmysly může pokusu o odeslání (Vložit) upraveném nebo další příkazy SQL ve snaze o získání neoprávněného přístupu nebo dojít k poškození databáze. Před přenosem vstupu uživatele na databázi vždy zkontrolujte, že je platný. Osvědčeným postupem je vždy nutné použít parametrických dotazů nebo uložené procedury, pokud je to možné.

## <a name="see-also"></a>Viz také:

- [Nástroje datové sady](../data-tools/dataset-tools-in-visual-studio.md)
