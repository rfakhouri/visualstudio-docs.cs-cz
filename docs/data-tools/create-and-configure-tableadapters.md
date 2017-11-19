---
title: "Vytvořit a nakonfigurovat TableAdapters | Microsoft Docs"
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- table adapters, creating
- creating TableAdapters
- data [Visual Studio], creating data components
- data [Visual Studio], TableAdapters
- data [Visual Studio], creating table adapters
ms.assetid: 08630d69-0d6c-4e8f-b42d-2922f45f8415
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 11086ba17f3f2fb7af99d76b3efadece4a23c426
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="create-and-configure-tableadapters"></a>Vytvoření a konfigurace TableAdapters
Objekty TableAdapter umožňují komunikaci mezi aplikací a databází. Připojení k databázi, spusťte dotazy nebo uložené procedury a vraťte se nová data tabulky nebo zadejte existující <xref:System.Data.DataTable> s vrácená data. TableAdapters můžete také odeslat aktualizovaná data z vaší aplikace zpět do databáze.  
  
TableAdapters jsou vytvořeny pro můžete provést jednu z následujících akcí:  
  
-   Spustit [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png) a vyberte buď **databáze** nebo **webové služby** typ zdroje dat.  
  
-   Přetáhněte objekty databáze z **Průzkumníka serveru** do **návrháře Dataset**.  
  
Můžete také vytvořit nové TableAdapter a nakonfigurovat ho se zdrojem dat tak, že přetáhnete TableAdapter z panelu nástrojů na prázdnou oblast v **návrháře Dataset** prostor.  
  
Úvod do prvků TableAdapters, najdete v části [vyplnění datové sady s použitím TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="use-the-tableadapter-configuration-wizard"></a>Pomocí Průvodce konfigurací TableAdapter  
Spustit **Průvodce nastavením TableAdapter** k vytváření a úpravám objektů TableAdapters a jejich přidružené DataTables. Můžete nakonfigurovat existující TableAdapter kliknutím pravým tlačítkem na jeho **návrháře Dataset**.  
  
![raddata Průvodce konfigurací adaptéru tabulky](../data-tools/media/raddata-table-adapter-configuration-wizard.png "raddata Průvodce konfigurací adaptéru tabulky")  
  
Pokud přetáhněte nové TableAdapter z panelu při **návrháře Dataset** má zaměřit, spustí průvodce a vyzve k zadání datových zdroje TableAdapter by se měly připojit. Na další stránce Průvodce zobrazí dotaz, jaký druh příkazy, měla by používat ke komunikaci s databází, příkazy SQL nebo uložené procedury. (Můžete nebude vidět, pokud konfigurujete TableAdapter, který je už přidružená ke zdroji dat.)  
  
-   Máte možnost vytvořit novou uloženou proceduru v podkladové databázi, pokud máte správná oprávnění pro databázi. Pokud tato oprávnění nemáte, to nebude možnost.  
  
-   Můžete také spustit existující uložené procedury **vyberte**, **vložit**, **aktualizace**, a **odstranit** příkazů TableAdapter. Uložené procedury, která je přiřazena k **aktualizace** příkazu, například se spustí, když `TableAdapter.Update()` metoda je volána.  
  
Namapujte parametry z vybraná uložená procedura na odpovídající sloupce v tabulce data. Například, pokud uložená procedura přijme parametr s názvem `@CompanyName` který předává do `CompanyName` sloupců v tabulce **zdrojový sloupec** z `@CompanyName` parametru `CompanyName`.  
  
> [!NOTE]
>  Uložené procedury, která je přiřazena k příkazu SELECT je spuštěn voláním metody TableAdapter tento název je v dalším kroku průvodce. Je výchozí metodou `Fill`, takže je kód, který se obvykle používá ke spuštění vyberte procedury `TableAdapter.Fill(tableName)`. Pokud změníte výchozí název z `Fill`, nahraďte `Fill` s názvem přiřadit a nahraďte skutečným názvem TableAdapter "TableAdapter" (například `CustomersTableAdapter`).  
  
-   Výběr **vytvořit metody k odeslání aktualizací přímo do databáze** je ekvivalentní nastavení `GenerateDBDirectMethods` vlastnost na hodnotu true. Možnost není dostupná, když původní příkaz jazyka SQL neposkytuje dostatek informací, nebo dotaz není možné aktualizovat dotaz. K této situaci může dojít, například v **připojení** dotazy a dotazy, které vrátí jednu hodnotu (skalární).  
  
**Pokročilé možnosti** v průvodci umožňují:  
- Generovat příkazy INSERT, UPDATE a DELETE na příkaz SELECT, který je definovaný na základě **generovat SQL příkazy** stránky
- Použít optimistickou metodu souběžného zpracování
- Určete, zda chcete aktualizovat tabulku dat po vložení a aktualizace příkazy se spouštějí  
  
## <a name="configure-a-tableadapters-fill-method"></a>Konfigurace TableAdapter Fill – metoda  
V některých případech můžete chtít změnit schéma tabulky TableAdapter. K tomuto účelu upravíte TableAdapter primární `Fill` metoda. TableAdapters jsou vytvořeny pomocí primární `Fill` metody, která definuje schéma tabulky přidružená data. Primární `Fill` metoda je založena na dotazu nebo uložené procedury, které jste zadali, když jste nakonfigurovali TableAdapter. Je první metodu (nejhornější) v tabulce dat v Návrháři DataSet.  
  
![TableAdapter s více dotazy](../data-tools/media/tableadapter.gif "TableAdapter")  
  
Veškeré změny, které provedete TableAdapter je hlavní `Fill` metoda se projeví ve schématu tabulky přidružená data. Například odebrání sloupce z dotazu v hlavní `Fill` metoda také odebere sloupce z tabulky přidružená data. Kromě toho odebrání sloupce z hlavní `Fill` metoda odebere sloupec žádné další dotazy pro tento TableAdapter.  
  
Průvodce konfigurací dotazu TableAdapter slouží k vytvoření a úprava dalších dotazů TableAdapter. Tyto další dotazy musí odpovídat schématu tabulky, pokud vracejí skalární hodnotu.  Každý další dotaz má název, který zadáte.  
 
Následující příklad ukazuje, jak volat další dotaz s názvem `FillByCity`:  
 
`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>Spusťte Průvodce konfigurací dotazu TableAdapter s nový dotaz  
  
1.  Otevřete datovou sadu v **návrháře Dataset**.  
  
2.  Pokud vytváříte nový dotaz, přetáhněte **dotazu** objektu z **datovou sadu** kartě **sada nástrojů** na <xref:System.Data.DataTable>, nebo vyberte **přidat dotazu**z místní nabídky TableAdapter. Můžete také přetáhnout **dotazu** objektu na prázdnou oblast **návrháře Dataset**, vytváří TableAdapter bez přidruženého <xref:System.Data.DataTable>. Tyto dotazy můžete pouze vrátí jeden hodnoty (skalární) nebo spusťte UPDATE, INSERT nebo odstranit příkazy v databázi.  
  
3.  Na **vybrat datové připojení** obrazovky vyberte nebo vytvořte připojení, který bude používat dotaz.  
  
    > [!NOTE]
    >  Tato obrazovka se zobrazí, pouze když návrháře nelze určit správné připojení používat, nebo když jsou k dispozici žádné připojení.  
  
4.  Na **zvolte typ příkazu** obrazovku, vyberte z následujících metod načítání dat z databáze:  
  
    -   **Používat příkazy SQL** umožní zadání příkazu SQL vyberte data z databáze.  
  
    -   **Vytvoření nové uložené procedury** umožňuje, aby průvodce vytvoříte nový uložené procedury (v databázi) na základě zadaného příkazu SELECT.  
  
    -   **Použití existující uložené procedury** umožňuje spouštět existující uložené procedury při spuštění dotazu.  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>Spusťte Průvodce konfigurací dotazu TableAdapter na existující dotaz  
  
-   Pokud upravujete existující dotaz TableAdapter, klikněte pravým tlačítkem na dotaz a potom vyberte **konfigurace** z místní nabídky.  
  
    > [!NOTE]
    >  Pravým tlačítkem myši na hlavním dotazu TableAdapter změní konfiguraci TableAdapter a <xref:System.Data.DataTable> schématu. Pravým tlačítkem myši na TableAdapter další dotaz, ale lze konfigurovat pouze vybraný dotaz. **Průvodce nastavením TableAdapter** překonfigurujete definici TableAdapter, zatímco Průvodce konfigurací dotazu TableAdapter překonfigurujete pouze vybraný dotaz.  
  
#### <a name="to-add-a-global--query-to-a-tableadapter"></a>Přidání globálního dotazu do TableAdapter  
  
-   *Globální dotazy* jsou dotazů SQL, které vrátí jednu hodnotu (skalární) nebo žádná hodnota. Globální funkce obvykle provádět operace databáze, například vložení, aktualizace, odstraní. Budou také shromažďovat informace, například počet zákazníků v tabulce nebo celkové náklady pro všechny položky v určitém pořadí.  
  
     Přidávání globálních dotazů přetažením **dotazu** objektu z **datovou sadu** kartě **sada nástrojů** na prázdnou oblast **návrháře Dataset**.  
  
-   Zadejte dotaz, který provede požadované úlohy, například `SELECT COUNT(*) AS CustomerCount FROM Customers`.  
  
    > [!NOTE]
    >  Přetahování **dotazu** přímo do objektu **návrháře Dataset** vytvoří metodu, která vrátí pouze skalární hodnota (jeden). Při dotazu nebo uložené procedury, kterou vyberete může vrátit více než jednu hodnotu, vrátí metoda, která je vytvořené průvodcem pouze jednu hodnotu. Například dotaz může vrátit první sloupec prvního řádku vrácená data.

## <a name="see-also"></a>Viz také
[Vyplnění datové sady s použitím objektů TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)