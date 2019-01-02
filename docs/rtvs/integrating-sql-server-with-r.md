---
title: Integrace s R systému SQL Server
description: Visual Studio podporuje vytváření a spouštění dotazů SQL z R a možnost R pro práci s uloženými procedurami.
ms.date: 06/25/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 2d8f9cd98d7f3fa794dedff87bfe4072906b075b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891732"
---
# <a name="work-with-sql-server-and-r"></a>Práce s využitím SQL serveru a jazyka R

Visual Studio skvělou podporu pro SQL Server pomáhá data, která odborníci pracovat s databází SQL a R prostřednictvím schopnost vytvářet a spouštět dotazy SQL a práce s uloženými procedurami.

> [!Note]
> Spolupráce s SQL a jazyka R, musíte mít nainstalovaný SQL Server Data Tools:
> - Visual Studio 2017: Spusťte instalační program sady Visual Studio a vyberte úložiště dat a zpracování úloh, která zahrnuje SQL Server Data tools.
> - Visual Studio 2015: postupujte podle pokynů [stáhnout SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (webu youtube.com)](https://www.youtube.com/watch?v=n4AYr0QIwdQ) přehled SQL serveru a jazyka R (3 m 03s). |

## <a name="create-and-run-sql-queries"></a>Vytváření a spouštění dotazů SQL

RTVS podporuje přidávání dotazů SQL do projekty v R, umožňuje iterativní vývoj dotazy SQL v rámci samostatné, dokud se nedostanete výsledky, které hledáte.

Chcete-li přidat soubor dotazu SQL, klikněte pravým tlačítkem na projekt v Průzkumníku řešení, vyberte **přidat** > **nová položka**a vyberte **dotaz SQL** typ souboru:

![Přidat dotaz SQL položku do projektu](media/sql-add-item.png)

Tento příkaz otevře soubor v editoru jazyka Transact-SQL Visual Studio, které poskytuje plnou podporou technologie IntelliSense pro SQL a možnost spouštět dotazy. Pro tyto funkce pro práci, budete muset připojit k databázi pomocí tlačítka připojit na panelu nástrojů editoru nebo pokusu o spuštění dotazu (**Ctrl**+**Shift**+**E** , která funguje taky na výběr). V obou případech se zobrazí dialogové okno připojení:

![Dialogové okno připojení SQL](media/sql-connection-dialog.png)

Jakmile se naváže připojení, můžete spouštět dotazy a analyzovat výsledky:

![Výsledky dotazu okno SQL](media/sql-query-results.png)

Editor jazyka Transact-SQL podporuje celou řadu dalších funkcí, jako je například zobrazení plán spuštění dotazu a dotaz ladicího programu.
Další informace najdete v tématu [pomocí editoru jazyka Transact-SQL pro úpravy a provádění skriptů](https://msdn.microsoft.com/library/hh272706.aspx).

## <a name="work-with-sql-server-stored-procedures"></a>Práce s uložených procedur SQL serveru

[SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services) (SQL Server 2016 nebo novějším) umožňuje vložení a spuštění kódu jazyka R z jazyka T-SQL uloženou proceduru. Můžete spustit kód R na počítači systému SQL Server, použít pro data vrácená z dotazu SQL a generovat sadu výsledků dotazu SQL, který může být zpracována další SQL nebo vrácen do klienta.

RTVS zjednodušuje proces jinak nepraktické a je náchylné kombinace SQL a kódu r. v jediném příkazu SQL, jak je popsáno v následujících částech:

- [Přidat připojení k databázi](#add-a-database-connection)
- [Psaní a testování uložené procedury SQL](#write-and-test-a-sql-stored-procedure)
- [Publikovat uložené procedury SQL](#publish-a-sql-stored-procedure)

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (webu youtube.com)](https://www.youtube.com/watch?v=dFKIT2OitWQ) pro přehled R a SQL, uložených procedur (6 min 09s). |

### <a name="add-a-database-connection"></a>Přidat připojení k databázi

1. Vyberte **nástroje R** > **Data** > **přidat připojení k databázi** zobrazíte **vlastnosti připojení** Dialogové okno. Sem zadejte název zdroje dat (SQL Server v tomto případě), název serveru, režim ověřování a název databáze. Vyberte **Test připojení** ověřit váš vstup, před jeho zavřením dialogu.

    ![Dialogové okno připojení SQL](media/sql-connection-string-dialog.png)

1. Jakmile vyberete **OK** s platné připojení, Visual Studio vygeneruje připojovací řetězec s názvem `dbConnection` v novém *nastavení. R* souboru. RTVS automaticky (spuštěno) zdroje tohoto souboru, takže připojení pomocí skriptů R můžete okamžitě použít:

![Soubor SQL Settings.R](media/sql-settings-dot-r.png)

### <a name="write-and-test-a-sql-stored-procedure"></a>Psaní a testování uložené procedury SQL

Pokud chcete přidat nové uložené procedury SQL, klikněte pravým tlačítkem na projekt, vyberte **přidat** > **nová položka**vyberte **uložená procedura SQL s jazykem R** ze seznamu šablon, Pojmenujte soubor a vyberte **OK**. Výchozí název souboru je *SqlSProc.R*; pro snadnější čtení, název souboru *StoredProcedure.R* se používá ve zbývající části tohoto oddílu. Pokud máte více uložených procedur, každého souboru musí mít jedinečný název souboru.

RTVS vytvoří tři soubory pro uložené procedury: *. R* soubor pro váš kód R *. Query.SQL* souboru pro kód SQL a *. Template.SQL* soubor, který kombinuje dvě. Druhé dvě zobrazí v Průzkumníku řešení jako podřízené objekty jsou *. R* souboru:

![Průzkumník řešení rozbalené zobrazení SQL uložená procedura s jazykem R](media/sql-solution-explorer-expanded.png)

*. R* souboru (*StoredProcedure.R* v tomto příkladu) je místo, kde píšete kód R. Výchozí obsah jsou:

```R
# @InputDataSet: input data frame, result of SQL query execution
# @OutputDataSet: data frame to pass back to SQL

# Test code
# library(RODBC)
# channel <- odbcDriverConnect(dbConnection)
# InputDataSet <- sqlQuery(channel, )
# odbcClose(channel)

OutputDataSet <- InputDataSet
```

Jednoduše ale nutné dodat, obdrží kód R datový rámec volá `InputDataSet` a vrátí výsledky v `OutputDataSet`, kódem šablony pouze kopírování vstup do výstupu.

> [!Note]
> Názvy těchto datových rámců jsou řízeny `@input_data_1_name` a `@output_data_1_name` parametrů při volání `sp_execute_external_script` systémové uložené procedury. Další informace o návrhu Tato konvence volání a některé příklady využití naleznete v tématu [sp_execute_external_script (Transact-SQL)](https://docs.microsoft.com/sql/relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql).

Další generovaný kód (v komentářích) poskytuje skript malý test, který se používá [RODBC balíčku](https://cran.r-project.org/web/packages/RODBC/index.html) přenášet příkaz SQL pro SQL Server, spusťte jej a načíst výsledek nastavit jako datový rámec R. Můžete odkomentovat tento test kód interaktivně psát kód R proti výsledek nastavte, že dostanete ze serveru SQL Server.

*. Query.SQL* souboru (*StoredProcedure.Query.sql* v tomto příkladu) zápisu a otestujte dotaz SQL, který generuje data pro `InputDataSet`. S tímto *.sql* souboru, editor poskytuje všechny běžné funkce jazyka Transact-SQL pro vás.

Jakmile budete spokojeni s vaším kódem SQL, ji integrovat s vaším kódem R přetažením *.sql* soubor do otevřete editor pro *. R* souboru. Na obrázku níže *StoredProcedure.Query.sql* byla přetažena na bod v *StoredProcedure.R* za čárkou v `sqlQuery(channel, )`:

![Čtení souboru SQL do proměnné řetězce jazyka R](media/sql-reference-sql-file-from-r.png)

Jak je vidět, tento krok jednoduché automaticky generuje kód R a otevřete *.sql* souboru, přečtěte si jeho obsah do řetězce a předejte jej do balíčku RODBC zásadu odeslat do systému SQL Server.

Teď můžete interaktivně zápisu R kód, který pracuje `InputDataSet` datového rámce podle potřeby. Mějte na paměti, že stačí vybrat kód R v editoru a odeslat do [interaktivní okno](interactive-repl-for-r-in-visual-studio.md) stisknutím kombinace kláves **Ctrl**+**Enter**.

*. Template.SQL* souboru (*StoredProcedure.Template.sql* v tomto příkladu), a konečně, obsahuje šablony pro generování SQL uložená procedura:

```sql
CREATE PROCEDURE [StoredProcedure]
AS
BEGIN
EXEC sp_execute_external_script @language = N'R'
    , @script = N'_RCODE_'
    , @input_data_1 = N'_INPUT_QUERY_'
--- Edit this line to handle the output data frame.
    WITH RESULT SETS (([MYNEWCOLUMN] NVARCHAR(max)));
END;
```

- `_RCODE_` Obsah se nahradí zástupný symbol *. R* souboru (například *StoredProcedure.R*).
- `_INPUT_QUERY_` Obsah se nahradí zástupný symbol *. Query.SQL* souboru (například *StoredProcedure.Query.sql*).
- Upravit `WITH RESULT SETS` klauzule, která popisují schéma sada výsledků vrácená z úložné procedury. Konkrétně identifikovat sloupce z `OutputDataSet` datového rámce, který chcete vracet volajícímu uložené procedury.

Například následující dotaz:

```sql
SELECT TOP 100 medallion, hack_license FROM nyctaxi_sample
```

Můžete využít následující `WITH RESULT SETS` klauzule k určení datové typy vrácených hodnot:

```sql
WITH RESULT SETS ((medallion NVARCHAR(max), hack_license NVARCHAR(max)));
```

### <a name="publish-a-sql-stored-procedure"></a>Publikovat uložené procedury SQL

1. Vyberte **nástroje R** > **Data** > **s možností publikování** příkazu nabídky.
1. V zobrazeném dialogovém okně Změnit **publikování:** k **databáze**zadejte cíl, vyberte **publikovat**, a RTVS vytvoří a publikuje uložené procedury:

    ![Uložená procedura dialogové okno pro publikování](media/sql-publish-with-options.png)

1. Chcete-li publikovat všechny uložené procedury v projektu, můžete použít **nástroje R** > **Data** > **publikovat uložené procedury** příkaz, který je také Tato možnost je k dispozici, když kliknete pravým tlačítkem na projekt v Průzkumníku řešení.

> [!Tip]
> Pokud máte Průzkumníku objektů SQL serveru otevřete v sadě Visual Studio, zobrazí se v publikovaných uložená procedura **programovatelnosti** > **uložené procedury** složky vaší databáze. Můžete ho spustit také z Průzkumníku objektů tak, že kliknete pravým tlačítkem a vyberete **provést proceduru**, nebo pomocí volání interaktivně z *.sql* okno dotazu.
