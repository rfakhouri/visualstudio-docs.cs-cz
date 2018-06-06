---
title: Hierarchická aktualizace
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, changed data
- data [Visual Basic], hierarchical update
- saving updated data
- datasets [Visual Basic], hierarchical update
- hierarchical update
- saving data, hierarchical update
- modified data saving
- updated data saving
- related tables, saving
ms.assetid: 68bae3f6-ec9b-45ee-a33a-69395029f54c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 442d6cd60597219c25b41f26ad8c2dc2151248ee
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747466"
---
# <a name="hierarchical-update"></a>Hierarchická aktualizace
*Hierarchická aktualizace* odkazuje na proces ukládání aktualizovaná data (z datové sady s dvou nebo více souvisejících tabulek) zpět do databáze při zachování pravidla referenční integrity. *Referenční integrity* odkazuje na pravidla konzistence poskytované omezení v databázi, která řídí chování vkládání, aktualizaci a odstraňování souvisejících záznamů. Například je referenční integrity, který vynutí vytvoření záznamu zákazníka před povolením objednávky vytvoření tohoto zákazníka.  Další informace o vztahy v datových sadách najdete v tématu [vztahy v datových sadách](../data-tools/relationships-in-datasets.md)

 Hierarchická aktualizace funkce používá `TableAdapterManager` ke správě `TableAdapter`s v typové datové sady. `TableAdapterManager` Součást [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-vygenerované třídy, takže není součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Při přetažení tabulku z okna zdrojů dat na stránku WPF nebo do formulářů Windows Visual Studio. přidá proměnné typu TableAdapterManager formulář nebo stránky a zobrazení v Návrháři na hlavním panelu součásti. Podrobné informace o `TableAdapterManager` třídy, najdete v části odkaz TableAdapterManager [TableAdapters](../data-tools/create-and-configure-tableadapters.md).

 Ve výchozím nastavení datové sady související tabulky jsou považovány za "pouze vztahy" což znamená, že ji nebude vynutit omezení cizího klíče. Toto nastavení v době návrhu můžete upravit pomocí návrháře Dataset. Vyberte řádek vztah mezi dvěma tabulkami se zprovoznit **vztah** dialogové okno. Zde provedené změny se určí, jak TableAdapterManager chová při odesílání změny v souvisejících tabulek zpět do databáze.

## <a name="enable-hierarchical-update-in-a-dataset"></a>Povolit hierarchické aktualizace v datové sadě
 Hierarchická aktualizace je standardně zapnuté pro všechny nové datové sady, které se přidají nebo vytvoření v projektu. Hierarchická aktualizace zapnout nebo vypnout pomocí nastavení **hierarchické aktualizace** vlastnost typové datové sady v datové sadě na **True** nebo **False**:

 ![Hierarchická aktualizace nastavení](../data-tools/media/hierarchical-update-setting.png)

## <a name="create-a-new-relation-between-tables"></a>Vytvořit nový vztah mezi tabulkami
 Pokud chcete vytvořit nový vztah mezi dvěma tabulkami, v Návrháři Dataset vyberte záhlaví každé tabulky, pak klikněte pravým tlačítkem a vyberte **přidat vztah**.

 ![Vztah nabídka přidat hierarchická aktualizace](../data-tools/media/hierarchical-update-add-relation-menu.png)

## <a name="understand-foreign-key-constraints-cascading-updates-and-deletes"></a>Pochopení omezení cizího klíče, kaskádové aktualizace a odstranění
 Je důležité pochopit, jak cizí klíč omezení a kaskádových chování v databázi se vytvoří v kódu generovaného datovou sadu.

 Ve výchozím nastavení, se generují tabulky dat v datové sady s relací (<xref:System.Data.DataRelation>) odpovídající vztahy v databázi. Ale relace v datové sadě nevygenerovala jako omezení cizího klíče. <xref:System.Data.DataRelation> Je nakonfigurovaný jako **vztah pouze** bez <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> nebo <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> v platnosti.

 Ve výchozím nastavení kaskádové aktualizace a kaskádové odstranění nejsou k dispozici i v případě, že vztah databáze je nastavena pomocí kaskádových aktualizace nebo odstranění v kaskádě zapnutý. Například vytvoření nového zákazníka a nové objednávky a pak pokusu o uložení dat může způsobit konflikt s omezení cizího klíče, které jsou definovány v databázi. Další informace najdete v tématu [vypnutí omezení při naplňování datové sady](turn-off-constraints-while-filling-a-dataset.md).

## <a name="set-the-order-to-perform-updates"></a>Nastavení pořadí provádění aktualizací
 Nastavení pořadí provádění aktualizací nastaví pořadí jednotlivých vložení, aktualizace a odstraní tento vyžadovaných pro uložení změněných dat. ve všech tabulkách datové sady. Pokud je povoleno hierarchické aktualizace, vložení se nejprve provádí pak aktualizací a poté se odstraní. `TableAdapterManager` Poskytuje `UpdateOrder` vlastnost, která může být nastaven na provést aktualizace jako první, pak vložení a odstranění.

> [!NOTE]
>  Je důležité si uvědomit, že je pořadí aktualizace všechny (včetně). To znamená když jsou provedeny aktualizace, vložení a pak odstranění jsou provést pro všechny tabulky v datové sadě.

 Nastavit `UpdateOrder` vlastnost po přetáhnete položky z [okno zdroje dat](add-new-data-sources.md) na formuláři, vyberte `TableAdapterManager` v komponent a pak nastavte `UpdateOrder` vlastnost v **vlastnosti** okno.

## <a name="create-a-backup-copy-of-a-dataset-before-performing-a-hierarchical-update"></a>Vytvořit záložní kopii sady před provedením hierarchické aktualizace
 Při ukládání dat (voláním `TableAdapterManager.UpdateAll()` metoda), `TableAdapterManager` pokusí aktualizovat data pro každou tabulku v rámci jedné transakce. Pokud žádnou část aktualizace pro všechny tabulky selže, celá transakce vrácena zpět. Ve většině případů vrátí vrácení zpět do původního stavu aplikace.

 Ale v některých případech můžete chtít obnovit datové sady ze záložní kopie. Příkladem toho může dojít, když používáte automatické zvýšení hodnoty. Pokud k uložení například operace se nezdaří, automatické zvýšení hodnoty se neresetují. v datové sadě a datová sada nadále vytvořit automatické zvyšování hodnoty. Zůstane mezera v číslování, která nemusí být přijatelné ve vaší aplikaci. V situacích, kde jedná se o problém `TableAdapterManager` poskytuje `BackupDataSetBeforeUpdate` vlastnost, která nahradí existující datovou sadu s záložní kopie, pokud se transakce nepovede.

> [!NOTE]
>  Záložní kopie je pouze v paměti, zatímco `TableAdapterManager.UpdateAll` metoda běží. Neexistuje tedy žádná programový přístup k této datové sadě zálohování protože ji nahradí původní datové sady nebo přejde mimo obor co nejrychleji `TableAdapterManager.UpdateAll` Metoda dokončení spuštění.

## <a name="modify-the-generated-save-code-to-perform-the-hierarchical-update"></a>Upravit vygenerovaného uložit kód a proveďte hierarchická aktualizace
 Uložte změny do databáze voláním z tabulek souvisejících dat v datové sadě `TableAdapterManager.UpdateAll` metoda a předávání názvu datové sady, který obsahuje související tabulky. Například spusťte `TableAdapterManager.UpdateAll(NorthwindDataset)` metody k odeslání aktualizací ze všech tabulek v NorthwindDataset k databázi back-end.

 Po uvolnění položky z **zdroje dat** okně kód je automaticky přidán do `Form_Load` událostí k naplnění každá tabulka ( `TableAdapter.Fill` metody). Kód je taky přidaný ke **Uložit** tlačítko klikněte na události <xref:System.Windows.Forms.BindingNavigator> k uložení dat z datové sady zpět do databáze ( `TableAdapterManager.UpdateAll` metoda).

 Uložit vygenerovaného kódu také obsahuje řádek kódu, který volá `CustomersBindingSource.EndEdit` metoda. Přesněji řečeno, zavolá <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda první <xref:System.Windows.Forms.BindingSource>přidaná do formuláře. Jinými slovy, tento kód se vygeneruje pouze pro první tabulka, která je přetažen z **zdroje dat** window do formuláře. <xref:System.Windows.Forms.BindingSource.EndEdit%2A> Volání potvrdí všechny změny, které jsou v procesu v všechny ovládací prvky vázané na data, které jsou aktuálně Upravovaný. Proto pokud stále má ovládací prvek vázané na data fokus a klikněte na tlačítko **Uložit** tlačítko všechna nevyřízená úpravy v tom, že jsou před skutečným uložit potvrzené ovládací prvek ( `TableAdapterManager.UpdateAll` metoda).

> [!NOTE]
>  Návrháři Dataset přidá jenom `BindingSource.EndEdit` kód pro první tabulka, která umístění na formuláři. Proto je nutné přidat řádek kódu pro volání `BindingSource.EndEdit` metoda pro každou související tabulku na formuláři. V tomto návodu, to znamená, budete muset přidat volání `OrdersBindingSource.EndEdit` metoda.

#### <a name="to-update-the-code-to-commit-changes-to-the-related-tables-before-saving"></a>Chcete-li aktualizovat kód potvrzení tabulky v relaci před uložením změn

1.  Dvakrát klikněte **Uložit** tlačítko <xref:System.Windows.Forms.BindingNavigator> otevřete **Form1** v editoru kódu.

2.  Přidá řádek kódu pro volání `OrdersBindingSource.EndEdit` metoda po řádek, který volá `CustomersBindingSource.EndEdit` metoda. Kód **Uložit** klikněte na tlačítko události by měl vypadat takto:

     [!code-vb[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/VisualBasic/hierarchical-update_1.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#1](../data-tools/codesnippet/CSharp/hierarchical-update_1.cs)]

Kromě potvrzení změn v tabulce souvisejících podřízených před uložením dat do databáze, můžete také chtít potvrzení nově vytvořený nadřazené záznamy před přidáním nové podřízené záznamy do datové sady. Jinými slovy můžete chtít přidat nový záznam nadřazené (zákazníka) k datové sadě než omezení cizích klíčů povolit nové podřízené záznamy (objednávky), který se má přidat k datové sadě. K tomu můžete použít podřízených `BindingSource.AddingNew` událostí.

> [!NOTE]
> Zda je nutné potvrdit nové nadřazené záznamy, závisí na typu ovládacího prvku, který se používá k vytvoření vazby ke zdroji dat. V tomto návodu pomocí jednotlivých ovládacích prvků pro vazbu v nadřazené tabulce. To vyžaduje další kód nový záznam nadřazené potvrzení. Pokud nadřazené záznamy byly místo zobrazeny v ovládacím prvku složité vazby, jako <xref:System.Windows.Forms.DataGridView>, tento další <xref:System.Windows.Forms.BindingSource.EndEdit%2A> volání pro nadřazený záznam nebude nutné. Je to proto, že základní funkce vazby dat ovládacího prvku zpracovává potvrzení nové záznamy.

#### <a name="to-add-code-to-commit-parent-records-in-the-dataset-before-adding-new-child-records"></a>Chcete-li přidat kód pro potvrzení nadřazené záznamy v sadě dat před přidáním nové podřízené záznamy

1.  Vytvoření obslužné rutiny událostí `OrdersBindingSource.AddingNew` událostí.

    -   Otevřete **Form1** v návrhovém zobrazení, vyberte **OrdersBindingSource** na hlavním panelu součást vyberte **události** v **vlastnosti** okně a dvakrát klikněte **AddingNew** událostí.

2.  Přidá řádek kódu do obslužné rutiny události, která volá `CustomersBindingSource.EndEdit` metoda. Kód `OrdersBindingSource_AddingNew` obslužné rutiny události by měl vypadat takto:

     [!code-vb[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/VisualBasic/hierarchical-update_2.vb)]
     [!code-csharp[VSProDataOrcasHierarchicalUpdate#2](../data-tools/codesnippet/CSharp/hierarchical-update_2.cs)]

## <a name="tableadaptermanager-reference"></a>TableAdapterManager odkaz
 Ve výchozím nastavení `TableAdapterManager` třídy se vygeneruje, když vytvoříte datovou sadu, která obsahuje související tabulky. Abyste zabránili generovaná třída, změňte hodnotu `Hierarchical Update` vlastnosti datové sady na hodnotu false. Při přetažení tabulku, která má vztah na návrhovou plochu formuláře Windows nebo WPF stránky, Visual Studio deklaruje členské proměnné třídy. Pokud nepoužijete vazby dat, budete muset ručně deklarovat proměnnou.

 `TableAdapterManager` Třída není součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Proto je nelze jej vyhledat v dokumentaci. Je vytvořen v době návrhu jako součást procesu vytváření datové sady.

 Toto jsou často používané metody a vlastnosti `TableAdapterManager` třídy:

|Člen|Popis|
|------------|-----------------|
|`UpdateAll` – Metoda|Uloží všechna data ze všech tabulek, data.|
|`BackUpDataSetBeforeUpdate` Vlastnost|Určuje, jestli se mají vytvořit si záložní kopii datovou sadu před spuštěním `TableAdapterManager.UpdateAll` metoda. Logická hodnota.|
|*Název tabulky* `TableAdapter` vlastnost|Představuje `TableAdapter`. Generovaný objekt `TableAdapterManager` obsahuje vlastnost pro každý `TableAdapter` spravuje. Například je generována datovou sadu s tabulkou Zákazníci a objednávky `TableAdapterManager` obsahující `CustomersTableAdapter` a `OrdersTableAdapter` vlastnosti.|
|`UpdateOrder` Vlastnost|Určuje pořadí jednotlivých insert, update a delete příkazy. Tuto možnost nastavíte na jednu z hodnot v `TableAdapterManager.UpdateOrderOption` výčtu.<br /><br /> Ve výchozím nastavení `UpdateOrder` je nastaven na **InsertUpdateDelete**. To znamená, které vloží, pak aktualizací a poté se odstraní se pro všechny tabulky v datové sadě.|

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)