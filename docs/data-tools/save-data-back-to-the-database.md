---
title: Ukládání dat zpět do databáze
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], validating data
- data validation, datasets
- data [Visual Studio], saving
- row version
- updating datasets, constraints
- datasets [Visual Basic], about datasets
- datasets [Visual Basic], merging
- updates, constraints in datasets
- saving data, about saving data
- datasets [Visual Basic], constraints
- TableAdapters
ms.assetid: afe6cb8a-dc6a-428b-b07b-903ac02c890b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6ecbf8e67b2c8db1b33fa1c5228d9d94f98e48c5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748056"
---
# <a name="save-data-back-to-the-database"></a>Ukládání dat zpět do databáze
Datová sada je kopie v paměti data. Pokud změníte data, je dobrým zvykem uložit tyto změny zpět do databáze. Můžete to udělat jedním ze tří způsobů:

-   Při volání jedné z metod aktualizace TableAdapter

-   Voláním jedné z metod TableAdapter DBDirect

-   Pomocí volání metody UpdateAll – na TableAdapterManager Visual Studio generuje pro vás, když datová sada obsahuje tabulky, které souvisejí s jinými tabulkami v datové sadě

Pokud data vytvoření vazby datovou sadu tabulek pro ovládací prvky na stránce formuláře Windows nebo XAML, architektura datová vazba vykonává všechnu práci za vás.

Pokud jste obeznámeni s TableAdapters, můžete přejít přímo na jednu z těchto témat:

|Téma|Popis|
|-----------|-----------------|
|[Vkládání nových záznamů do databáze](../data-tools/insert-new-records-into-a-database.md)|Postup aktualizace a vloží pomocí TableAdapters nebo příkaz objektů|
|[Aktualizace dat pomocí objektu TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md)|Postup aktualizace s TableAdapters|
|[Hierarchická aktualizace](../data-tools/hierarchical-update.md)|Provádění aktualizací z datové sady s minimálně dva související tabulky|
|[Zpracování výjimky souběžnosti](../data-tools/handle-a-concurrency-exception.md)|Postupy: zpracování výjimky, když dva uživatelé pokusí změnit stejná data v databázi ve stejnou dobu|
|[Postupy: ukládání dat pomocí transakce](../data-tools/save-data-by-using-a-transaction.md)|Jak k uložení dat v transakci pomocí System.Transactions – obor názvů a objekt TransactionScope|
|[Návod: Uložení dat do transakce](../data-tools/save-data-in-a-transaction.md)|Návod, který vytvoří aplikaci Windows Forms k předvedení ukládání dat do databáze v transakci|
|[Uložení dat do databáze (více tabulek)](../data-tools/save-data-to-a-database-multiple-tables.md)|Postup úpravy záznamů a uložit změny ve více tabulek zpět do databáze|
|[Uložení dat z objektu do databáze](../data-tools/save-data-from-an-object-to-a-database.md)|Jak předat data z objektu, který není v datové sadě k databázi pomocí TableAdapter DbDirect metody|
|[Ukládání dat pomocí metod TableAdapter DBDirect](../data-tools/save-data-with-the-tableadapter-dbdirect-methods.md)|Jak používat k odesílání dotazů SQL přímo do databáze TableAdapter|
|[Uložení datové sady ve formátu XML](../data-tools/save-a-dataset-as-xml.md)|Jak uložit datové sady do dokumentu XML|

## <a name="two-stage-updates"></a>Dvoufázová aktualizace
 Aktualizace zdroje dat je dvoustupňový proces. Prvním krokem je aktualizace datovou sadu s nové záznamy, záznamy změněné nebo odstraněné záznamy. Pokud vaše aplikace nikdy odešle tyto změny zpět do zdroje dat, pak jste hotovi s aktualizací.

 Pokud odešlete změny zpět do databáze, druhý krok je povinný. Pokud nepoužíváte ovládací prvky vázané na data, budete muset ručně zavolat metodu aktualizace stejné TableAdapter (nebo adaptér dat), který jste použili k naplnění datové sady. Pro přesun dat z jednoho zdroje dat na jiný nebo aktualizaci více zdrojů dat však můžete použít také různé adaptéry, například. Pokud nejsou použití datových vazeb a ukládají změny pro tabulky v relaci, budete muset ručně vytvořit instanci proměnné automaticky vygenerované třídy TableAdapterManager a potom volejte příslušnou metodu UdpateAll.

 ![Visual Basic datovou sadu aktualizací](../data-tools/media/vbdatasetupdates.gif) aktualizace dvoustupňový proces a roli DataRowVersion v úspěšné aktualizaci

 Datové sady obsahuje kolekce tabulek, které obsahují kolekce řádků. Pokud chcete aktualizovat příslušný zdroj dat později, musíte použít metody pro vlastnost DataTable.DataRowCollection při přidávání nebo odebírání řádků. Tyto metody proveďte potřebné pro aktualizaci zdroje dat sledování změn. Když zavoláte kolekci RemoveAt na vlastnost řádků, nebude odstranění oznamovat zpět do databáze.

## <a name="merge-datasets"></a>Sloučení datové sady
 Můžete aktualizovat obsah sady pomocí *slučování* ho s jinou datovou sadu. To zahrnuje kopírování obsahu *zdroj* datové sady do volání datovou sadu (označují jako *cíl* datové sady). Při slučování datové sady, nové záznamy v sadě zdroje dat se přidají do cílové datové sady. Kromě toho navíc sloupců v datové sadě zdroje jsou přidány do cílového datovou sadu. Slučování datové sady je užitečné, když máte místní datovou sadu a získat druhý datové sady z jiné aplikace. Je také užitečné, když druhý datové sady můžete získat z komponenty, jako jsou webové služby XML, nebo když potřebujete k integraci dat z více datových sad.

 Při slučování datové sady, můžete předat argumentem logická hodnota (`preserveChanges`), která oznamuje <xref:System.Data.DataSet.Merge%2A> metoda zda chcete zachovat existující změny v datové sadě cíl. Protože datové sady udržovat více záznamů verzí, je důležité mít na paměti, že je více než jedna verze záznamy slučování. Následující tabulka ukazuje, jak je sloučen záznam v dvě datové sady:

|DataRowVersion|Cíl datové sady|Zdroj datové sady|
|--------------------|--------------------|--------------------|
|Původní|James Wilson|James C. Wilson|
|Aktuální|Jima Wilson|James C. Wilson|

 Volání <xref:System.Data.DataSet.Merge%2A> metoda v předchozí tabulce s `preserveChanges=false targetDataset.Merge(sourceDataset)` výsledkem následující:

|DataRowVersion|Cíl datové sady|Zdroj datové sady|
|--------------------|--------------------|--------------------|
|Původní|James C. Wilson|James C. Wilson|
|Aktuální|James C. Wilson|James C. Wilson|

 Volání <xref:System.Data.DataSet.Merge%2A> metoda s `preserveChanges = true targetDataset.Merge(sourceDataset, true)` výsledkem následující:

|DataRowVersion|Cíl datové sady|Zdroj datové sady|
|--------------------|--------------------|--------------------|
|Původní|James C. Wilson|James C. Wilson|
|Aktuální|Jima Wilson|James C. Wilson|

> [!CAUTION]
>  V `preserveChanges = true` scénář, pokud <xref:System.Data.DataSet.RejectChanges%2A> metoda je volána na záznam v datové sadě target a pak se vrátí do původního data z *zdroj* datovou sadu. To znamená, že pokud se pokusíte aktualizovat původní zdroj dat v datové sadě cíl, nemusí být schopna nalézt původní řádek aktualizovat. Naplnění jinou datovou sadu s aktualizované záznamy ze zdroje dat a pak provedením sloučení, aby se zabránilo narušení souběžnosti můžete zabránit narušení souběžnosti. (Porušení souběžnosti nastane, když se jiný uživatel upraví záznam ve zdroji dat po naplní datovou sadu.)

## <a name="update-constraints"></a>Omezení aktualizace
 Změnit existující řádek dat, přidat nebo aktualizovat data v jednotlivých sloupcích. Pokud datová sada obsahuje omezení (jako jsou cizí klíče nebo omezení použití hodnot Null), je možné, že záznam dočasně lze v chybovém stavu jako ho aktualizujete. To znamená může být ve stavu chyby po dokončení aktualizace jeden sloupec, ale předtím, než dojde k dalšímu.

 Aby se zabránilo narušení předčasné omezení můžete dočasně pozastavit aktualizace omezení. To má dva účely:

-   Chyba brání hlášeny po dokončení aktualizace jeden sloupec, ale nezahájili jiné aktualizace.

-   Zabraňuje určité aktualizace události z se vyvolá (událostí, které se často používají pro ověření).

> [!NOTE]
>  V systému Windows Forms, architektura vazby dat, která je integrovaná v kolekci datagrid pozastaví omezení kontrolu, dokud se aktivuje mimo řádek, a není nutné explicitně volání <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, nebo <xref:System.Data.DataRow.CancelEdit%2A> metody.

 Omezení jsou automaticky zakázán, když <xref:System.Data.DataSet.Merge%2A> metoda je volána, datové sady. Po dokončení, pokud nejsou žádná omezení na datovou sadu, která nemůže být povolena, sloučení <xref:System.Data.ConstraintException> je vyvolána výjimka. V takovém případě <xref:System.Data.DataSet.EnforceConstraints%2A> je nastavena na `false,` a vyřešit všechny narušení omezení před resetováním <xref:System.Data.DataSet.EnforceConstraints%2A> vlastnost, která má `true`.

 Po dokončení aktualizace se můžete znovu povolit kontrola omezení, která také znovu povolí aktualizace události a vyvolá je.

 Další informace o pozastavení událostí najdete v tématu [vypnutí omezení při naplňování datové sady](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

## <a name="dataset-update-errors"></a>Chyby aktualizace datové sady
 Při aktualizaci záznamu v datové sadě, je možné chyby. Například může nechtěně zapisovat data nesprávného typu ke sloupci, nebo data, která je příliš dlouhý nebo data, která má jiný problém integrity. Nebo můžete mít specifické pro aplikaci ověřovací kontroly, které může být spojeno vlastní chyby během jakékoli fázi událost aktualizace. Další informace najdete v tématu [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md).

## <a name="maintaining-information-about-changes"></a>Zachování informací o změnách
 Informace o změnách v datové sadě zachovaný dvěma způsoby: pomocí označování řádky, které označují, že se změnila (<xref:System.Data.DataRow.RowState%2A>) a tak více kopií záznamu (<xref:System.Data.DataRowVersion>). Procesy pomocí těchto informací můžete určit, co se změnilo v datové sadě a ke zdroji dat může odesílat příslušné aktualizace.

### <a name="rowstate-property"></a>Vlastnost RowState
 <xref:System.Data.DataRow.RowState%2A> Vlastnost <xref:System.Data.DataRow> objektu je hodnota, která poskytuje informace o stavu konkrétního řádku dat.

 V následující tabulce jsou možné hodnoty <xref:System.Data.DataRowState> výčtu:

|Hodnota DataRowState|Popis|
|------------------------|-----------------|
|<xref:System.Data.DataRowState.Added>|Řádek byl přidán jako položku, kterou chcete <xref:System.Data.DataRowCollection>. (V řádku v tomto stavu nemá odpovídající původní verzi, protože složka neexistuje při poslední <xref:System.Data.DataRow.AcceptChanges%2A> byla volána metoda).|
|<xref:System.Data.DataRowState.Deleted>|Řádek byl odstraněn, pomocí <xref:System.Data.DataRow.Delete%2A> z <xref:System.Data.DataRow> objektu.|
|<xref:System.Data.DataRowState.Detached>|Řádek byl vytvořen, ale není součástí žádné <xref:System.Data.DataRowCollection>. A <xref:System.Data.DataRow> objekt je v tomto stavu okamžitě po jeho vytvoření, než byl přidán do kolekce a poté, co byl odebrán z kolekce.|
|<xref:System.Data.DataRowState.Modified>|Hodnota sloupce v řádku změnil nějakým způsobem.|
|<xref:System.Data.DataRowState.Unchanged>|Řádek nebyl změněn od <xref:System.Data.DataRow.AcceptChanges%2A> poslední byla volána.|

### <a name="datarowversion-enumeration"></a>DataRowVersion – výčet
Datové sady udržovat několik verzí záznamů. <xref:System.Data.DataRowVersion> Pole lze použít při načítání hodnota nalezena v <xref:System.Data.DataRow> pomocí <xref:System.Data.DataRow.Item%2A> vlastnost nebo <xref:System.Data.DataRow.GetChildRows%2A> metodu <xref:System.Data.DataRow> objektu.

V následující tabulce jsou možné hodnoty <xref:System.Data.DataRowVersion> výčtu:

|Hodnota DataRowVersion|Popis|
|--------------------------|-----------------|
|<xref:System.Data.DataRowVersion.Current>|Aktuální verze záznam obsahuje všechny změny provedené v záznamu od posledního <xref:System.Data.DataRow.AcceptChanges%2A> byla volána. Pokud řádek byl odstraněn, není žádná aktuální verze.|
|<xref:System.Data.DataRowVersion.Default>|Výchozí hodnota záznamu, jak je definované ve zdroji dataset schématu nebo data.|
|<xref:System.Data.DataRowVersion.Original>|Původní verze záznamu je kopie záznamu, stejně jako tomu bylo, že byly potvrzeny poslední změny času v datové sadě. V praxi je to obvykle verzi záznam jako čtení ze zdroje dat.|
|<xref:System.Data.DataRowVersion.Proposed>|Navrhované verze na záznam, který je k dispozici dočasně v době, kdy jste uprostřed aktualizace – to znamená, mezi tím, kdy jste volali metodu <xref:System.Data.DataRow.BeginEdit%2A> metoda a <xref:System.Data.DataRow.EndEdit%2A> metoda. Obvykle se navrhované verze záznamu v obslužnou rutinu události, jako <xref:System.Data.DataTable.RowChanging>. Vyvolání <xref:System.Data.DataRow.CancelEdit%2A> metoda vrátí zpět změny a odstraní navrhované verzi datovým řádkem.|

 Aktuální a původní verze jsou užitečné, pokud se ke zdroji dat přenášejí informace o aktualizaci. Při aktualizaci odeslání ke zdroji dat, nové informace pro databázi je obvykle v aktuální verzi záznamu. Informace z původní verze je používaná k nalezení na aktualizaci záznamu.

 Například v případě změnou primární klíč záznamu potřebovat způsob, jak najít správný záznamu ve zdroji dat za účelem aktualizace změny. Pokud neexistovala žádná původní verze by být záznam s největší pravděpodobností připojí ke zdroji dat, což pouze v záznamu o velmi nežádoucí, ale v jeden záznam, který je nesprávné a je zastaralý. Dvě verze se také používají v ovládacím prvku souběžnosti. Původní verze na záznam ve zdroji dat k určení, jestli záznam změnil vzhledem k tomu, že byla načtena do datové sady, můžete porovnat.

 Navrhované verze je užitečné, když je třeba provést ověření před ve skutečnosti potvrzením změny do datové sady.

 I v případě, že záznamy změnily, nejsou k dispozici vždy původním nebo aktuální verze příslušném řádku. Při vložení nového řádku do tabulky, není žádná původní verze na aktuální verzi. Podobně pokud voláním tabulky odstraníte řádek `Delete` metoda, je původní verze, ale žádný aktuální verzi.

 Můžete otestovat, zda existuje na konkrétní verzi záznamu pomocí dotazu na řádek dat <xref:System.Data.DataRow.HasVersion%2A> metoda. Buď verzi záznam můžete přejít pomocí předání <xref:System.Data.DataRowVersion> hodnota výčtu jako volitelný argument při žádosti o hodnotě sloupce.

## <a name="getting-changed-records"></a>Získávání změněné záznamy
 Je běžnou praxí nechcete aktualizovat každý záznam v datové sadě. Uživatel například může pracovat s Windows Forms <xref:System.Windows.Forms.DataGridView> ovládací prvek, který je zobrazeno více záznamů. Uživatel může však aktualizovat pouze několik záznamů, odstraňte jednu a vložit nový. Datové sady a data tabulky poskytují metodu (`GetChanges`) pro vrácení jenom na řádky, které byly upraveny.

 Můžete vytvořit podmnožiny změněné záznamy pomocí `GetChanges` metoda tabulky dat (<xref:System.Data.DataTable.GetChanges%2A>) nebo datové sady (<xref:System.Data.DataSet.GetChanges%2A>) sám sebe. Když zavoláte metodu pro tabulku dat, vrátí kopii tabulky se pouze změněné záznamy. Podobně když zavoláte metodu na datovou sadu, získáte novou datovou sadu s pouze změněné záznamy v ní.

 `GetChanges` samostatně vrátí všechny změněné záznamy. Naproti tomu předáním požadovanou <xref:System.Data.DataRowState> jako parametr, který se `GetChanges` metodu, můžete zadat jaké podmnožinu změněné záznamy, které chcete: nově záznamů, záznamy, které jsou označené k odstranění, odpojit záznamy k přidání nebo úpravě záznamů.

 Získávání podmnožinu změněné záznamy je užitečné, pokud chcete odeslat záznamy do jiné součásti pro zpracování. Místo odesílání celou datovou sadu, můžete snížit režii při komunikaci s komponentou jiných získáním pouze záznamy, které potřebuje komponentu.

## <a name="committing-changes-in-the-dataset"></a>Potvrzení změn v datové sadě
 Jakmile jsou změny v datové sadě, <xref:System.Data.DataRow.RowState%2A> vlastnost změněných řádků je nastavena. Vytvořeno, udržuje a k dispozici vám aktuální a původní verze záznamů <xref:System.Data.DataRowView.RowVersion%2A> vlastnost. Metadata, která je uložená ve vlastnostech těchto změněných řádků je nutné pro zdroj dat a odesílání správné aktualizace.

 Pokud změny odráží aktuální stav zdroje dat, musíte už udržovat tyto informace. Obvykle nejsou dvakrát při datovou sadu a zdroj synchronizace:

-   Ihned po načetli jste informace do datové sady, například při čtení dat ze zdroje.

-   Po odeslání změn z datové sady do zdroje dat (ale ne dřív, protože by dojít ke ztrátě informace o změnách, které je nutné k odeslání změn do databáze).

Můžete provést čekající změny datovou sadu voláním <xref:System.Data.DataSet.AcceptChanges%2A> metoda. Obvykle <xref:System.Data.DataSet.AcceptChanges%2A> je volána v následujících časech:

-   Po načtení datovou sadu. Pokud zavedete datovou sadu voláním TableAdapter `Fill` metoda pak adaptéru pro vás automaticky provádí změny. Ale Pokud zavedete sloučením jiné datové sady do ní datovou sadu, pak budete muset provést změny ručně.

    > [!NOTE]
    >  Můžete zabránit adaptér automaticky potvrzení změny při volání `Fill` metoda nastavením `AcceptChangesDuringFill` vlastnost adaptér, který má `false`. Pokud je nastaven na hodnotu `false`, pak se <xref:System.Data.DataRow.RowState%2A> od jednotlivých řádků, který je vložen během výplně je nastaven na <xref:System.Data.DataRowState.Added>.

-   Po odeslání změn datové sady na jiný proces, jako jsou webové služby XML.

    > [!CAUTION]
    >  Provádění změn tímto způsobem se vymaže všechny informace o změně. Není potvrzení změny až po můžete dokončit provádění operací, které vyžadují aplikaci vědět, jaké změny byly provedeny v datové sadě.

Tato metoda provede následující akce:

-   Zapíše <xref:System.Data.DataRowVersion.Current> verze záznamu do jeho <xref:System.Data.DataRowVersion.Original> verze a přepíše původní verze.

-   Odebere všechny řádky, ve kterém <xref:System.Data.DataRow.RowState%2A> je nastavena na <xref:System.Data.DataRowState.Deleted>.

-   Nastaví <xref:System.Data.DataRow.RowState%2A> vlastnost záznam o <xref:System.Data.DataRowState.Unchanged>.

<xref:System.Data.DataSet.AcceptChanges%2A> Metoda je k dispozici ve třech úrovních. Můžete volat na <xref:System.Data.DataRow> změny objektu k potvrzení pro právě tento řádek. Můžete ho také zavolat na <xref:System.Data.DataTable> objekt, který chcete potvrdit všechny řádky v tabulce. Nakonec můžete volat na <xref:System.Data.DataSet> objekt, který chcete použít všechny čekající změny ve všech záznamech všech tabulek datové sady.

Následující tabulka popisuje, jaké změny se potvrdí podle toho, co objekt, že metoda je volána v.

|Metoda|Výsledek|
|------------|------------|
|<xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>|Změny se potvrdí pouze na konkrétní řádek.|
|<xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>|Změny se potvrdí na všechny řádky v tabulce konkrétní.|
|<xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>|Změny se potvrdí na všechny řádky ve všech tabulkách datové sady.|

> [!NOTE]
>  Pokud zavedete datovou sadu voláním TableAdapter `Fill` metoda, není nutné explicitně přijetí změn. Ve výchozím nastavení `Fill` volání metod `AcceptChanges` metoda po jejím dokončení naplnění dat tabulky.

 Související metody <xref:System.Data.DataSet.RejectChanges%2A>, vrátí zpět změny zkopírováním <xref:System.Data.DataRowVersion.Original> verze zpět do <xref:System.Data.DataRowVersion.Current> verzi záznamy. Nastaví taky <xref:System.Data.DataRow.RowState%2A> z jednotlivých záznamů zpátky do <xref:System.Data.DataRowState.Unchanged>.

## <a name="data-validation"></a>Ověřování dat
 Pro ověření, že data v aplikaci splňuje požadavky na procesy, které je předán do, je často nutné přidat ověření. To může zahrnovat kontrola, zda je uživatelský vstup ve formuláři správný, ověření dat, která se posílají do vaší aplikace v jiné aplikaci, nebo i kontrola, zda informace, které se počítá v rámci vaší komponenty spadá do omezení zdroje dat. a požadavky na aplikace.

 Můžete ověřit data v několika způsoby:

-   V obchodní vrstvě přidáním kódu do vaší aplikace ověřit data. Datová sada je jednom místě, můžete to provést. Datová sada obsahuje některé z výhod back-end ověřování – například možnost ověřit změny, jako je změna hodnoty řádků a sloupců. Další informace najdete v tématu [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md).

-   V prezentační vrstvě přidáním ověření do formulářů. Další informace najdete v tématu [ověření vstupu uživatele v systému Windows Forms](/dotnet/framework/winforms/user-input-validation-in-windows-forms).

-   V datech back-end, odesílá data do zdroje dat – například databáze – a díky kterému jej k přijetí nebo odmítnutí data. Pokud pracujete s databázi, která má pokročilé zařízení pro ověřování dat a poskytuje informace o chybě, to může být praktické přístup, protože můžete ověřit data bez ohledu na to, které pocházejí z. Tento přístup však nemusí zohlednit požadavky na ověření specifické pro aplikaci. Kromě toho má zdroj dat, ověřit data může způsobit odezev množství ke zdroji dat, v závislosti na tom, jak vaše aplikace usnadňuje řešení chyb ověřování aktivováno back-end.

    > [!IMPORTANT]
    >  Při použití datové příkazy s <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> vlastnost, která je nastavena na <xref:System.Data.CommandType.Text>, pečlivě zkontrolujte informace, které se odesílá z klienta před jeho odesláním k vaší databázi. Uživatelé se zlými úmysly může pokusu o odeslání (Vložit) upraveném nebo další příkazy SQL ve snaze o získání neoprávněného přístupu nebo dojít k poškození databáze. Před přenosem vstupu uživatele na databázi vždy zkontrolujte, že je platný. Je osvědčeným postupem vždy nutné použít parametrických dotazů nebo uložené procedury, pokud je to možné.

## <a name="transmitting-updates-to-the-data-source"></a>Aktualizace přenosu ke zdroji dat
Poté, co byly provedeny změny v datové sadě, může přenášet změny ke zdroji dat. Nejčastěji to provedete pomocí volání `Update` metoda TableAdapter (nebo adaptér dat). Metoda smyčky prostřednictvím každý záznam v tabulce dat určuje, jaký typ aktualizace je vyžadováno (aktualizace, vložení nebo odstranění), pokud existuje, a poté spustí příslušný příkaz.

 Jako obrázek o tom, jak jsou provedeny aktualizace Předpokládejme, že vaše aplikace používá datovou sadu, která obsahuje do jedné tabulky datového. Aplikace načte dva řádky z databáze. Po načtení tabulka v paměti dat vypadat třeba takto:

```sql
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Unchanged)    c400         Nancy Buchanan    Pending
```

 Aplikace změní stav Nancy Kocián na "Preferované." V důsledku této změny, hodnota <xref:System.Data.DataRow.RowState%2A> změny vlastností pro tento řádek z <xref:System.Data.DataRowState.Unchanged> k <xref:System.Data.DataRowState.Modified>. Hodnota <xref:System.Data.DataRow.RowState%2A> vlastnost pro první řádek zůstane <xref:System.Data.DataRowState.Unchanged>. Datová tabulka nyní vypadat třeba takto:

```sql
(RowState)     CustomerID   Name             Status
(Unchanged)    c200         Robert Lyon      Good
(Modified)     c400         Nancy Buchanan    Preferred
```

 Aplikace nyní zavolat `Update` metoda přenést datové sady do databáze. Metoda pak zkontroluje každý řádek. Pro první řádek metodu přenáší žádný příkaz jazyka SQL do databáze, protože tento řádek se nezměnila, protože byl původně načtených z databáze.

 Pro druhý řádek, ale `Update` metoda automaticky vyvolá příkaz správná data a odesílá do databáze. Specifickou syntaxi příkazu SQL, závisí na dialekt podporuje základní úložiště dat SQL. Ale následující obecné vlastnosti příkazu SQL přenášená stojí:

-   Velikost přenášených příkaz jazyka SQL je příkazu UPDATE. Adaptér věděl, může použít příkaz UPDATE, protože hodnota <xref:System.Data.DataRow.RowState%2A> vlastnost je <xref:System.Data.DataRowState.Modified>.

-   Velikost přenášených příkaz SQL obsahuje klauzuli WHERE označující, že je cílem příkazu UPDATE na řádku kde `CustomerID = 'c400'`. Tato část příkazu SELECT odlišuje cílový řádek ze všech ostatních, protože `CustomerID` je primární klíč, který cílové tabulky. Informace pro klauzuli WHERE je odvozený od původní verze záznamu (`DataRowVersion.Original`), v případě, že hodnoty, které jsou požadovány k identifikaci řádek změnily.

-   Velikost přenášených příkaz SQL obsahuje klauzuli SET, nastavení na nové hodnoty upravené sloupce.

    > [!NOTE]
    > Pokud TableAdapter `UpdateCommand` vlastnost byla nastavena na název uložené procedury, adaptér není vytvoření příkazu SQL. Místo toho vyvolá uložená procedura s příslušnými parametry předané.

## <a name="passing-parameters"></a>Předávání parametrů
 Obvykle použijete parametry k předání záznamy, které se chystáte být aktualizována v databázi.  Když TableAdapter `Update` spuštěním příkazu UPDATE metody, je nutné zadat parametr hodnoty. Získá tyto hodnoty z `Parameters` kolekce pro příkaz příslušná data – v takovém případě `UpdateCommand` objekt v TableAdapter.

 Pokud jste použili sady Visual Studio tools pro generování dat adaptér, `UpdateCommand` objekt obsahuje kolekci parametrů, které odpovídají každý parametr zástupný symbol v příkazu.

 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A?displayProperty=fullName> Vlastnost každý parametr odkazuje na sloupec v tabulce data. Například `SourceColumn` vlastnost `au_id` a `Original_au_id` parametry je nastaven na jakémkoli sloupec v tabulce dat obsahuje id autora. Když adaptéru `Update` metoda běží ve sloupci id čte Autor z záznam, který se právě aktualizuje a výplní hodnot příkazu SELECT.

 V příkazu UPDATE budete muset zadat obě novými hodnotami (ty, které budou zapisovat do záznamu) stejně jako starý hodnoty (tak, aby záznamu může být umístěno v databázi). Proto existují dva parametry pro každou hodnotu: jeden pro klauzuli SET a jinou pro klauzuli WHERE. Oba parametry čtení dat ze záznamu, který se právě aktualizuje, ale získají různé verze na základě parametru na hodnotu ve sloupci <xref:System.Data.SqlClient.SqlParameter.SourceVersion> vlastnost. Parametr pro klauzuli SET získá aktuální verze a parametr pro klauzuli WHERE získá původní verze.

> [!NOTE]
> Můžete také nastavit hodnoty v `Parameters` kolekce sami v kódu, což by obvykle provést v obslužné rutiny události pro adaptér dat <xref:System.Data.DataTable.RowChanging> událostí.

## <a name="see-also"></a>Viz také:

- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Vytvoření a konfigurace TableAdapters](create-and-configure-tableadapters.md)
- [Aktualizace dat pomocí objektu TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md)
- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Ověřování dat](validate-data-in-datasets.md)
- [Ukládání dat](../data-tools/saving-data.md)