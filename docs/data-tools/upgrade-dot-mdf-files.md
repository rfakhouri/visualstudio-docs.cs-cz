---
title: Upgrade souborů .mdf
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Express
- SQL Server LocalDB
- LocalDB
- SQLEXPRESS
- upgrading SQLExpress to SQLExpress
- upgrading to LocalDB
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: cf68127d875ba4c785f10319cabdd96a3c11adc2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996191"
---
# <a name="upgrade-mdf-files"></a>Upgrade souborů .mdf

Toto téma popisuje možnosti pro upgrade databázového souboru (*.mdf*) po instalaci novější verze sady Visual Studio. Obsahuje pokyny pro následující úlohy:

- Upgrade databázového souboru, který chcete používat novější verzi SQL Server Express LocalDB

- Upgrade databázového souboru pro použití novější verze systému SQL Server Express

- Práce s databázového souboru v sadě Visual Studio při zachování kompatibility se starší verzí systému SQL Server Express nebo LocalDB

- Ujistěte se, SQL Server Express. databázový stroj výchozí

Můžete použít Visual Studio otevřete projekt, který obsahuje soubor databáze (*.mdf*), která byla vytvořena pomocí starší verze systému SQL Server Express nebo LocalDB. Ale dalším vývoji projektu v sadě Visual Studio, musíte mít verzi systému SQL Server Express nebo LocalDB nainstalované ve stejném počítači jako Visual Studio, nebo musíte upgradovat tento databázový soubor. Pokud provedete upgrade databázového souboru, nebude možné k němu přistupovat pomocí starší verze systému SQL Server Express nebo LocalDB.

Také můžete být vyzváni k upgradu databáze soubor, který byl vytvořen pomocí dřívější verzi serveru SQL Server Express nebo LocalDB, pokud není kompatibilní s instancí systému SQL Server Express nebo LocalDB, který je aktuálně nainstalované verzi souboru. Chcete-li vyřešit tento problém, Visual Studio vás vyzve k upgradu soubor.

> [!IMPORTANT]
> Doporučujeme, abyste před provedením upgradu zálohovat soubor databáze.

> [!WARNING]
> Pokud provádíte upgrade *.mdf* souboru, který byl vytvořen v LocalDB 2014 (V12) 32 bitů na LocalDB 2016 (V13) nebo novější, nebude možné znovu otevřete soubor v 32bitové verzi LocalDB.

Než spustíte upgrade databáze, zvažte následující kritéria:

-   Neprovádějte upgrade, pokud budete chtít pracovat na projektu ve starší verzi a novější verze sady Visual Studio.

-   Neprovádějte upgrade, pokud vaše aplikace se použije v prostředí, které používá namísto LocalDB systému SQL Server Express.

-   Pokud vaše aplikace používá vzdálená připojení, nemusíte upgradovat, protože LocalDB nepřijme.

-   Neprovádějte upgrade, pokud vaše aplikace využívá v Internetové informační služby (IIS).

-   Pokud chcete otestovat databázových aplikací v prostředí izolovaného prostoru, ale nechcete, aby ke správě databáze, zvažte možnost upgradovat.

### <a name="to-upgrade-a-database-file-to-use-the-localdb-version"></a>Upgrade databázového souboru pro použití LocalDB verze

1.  V **Průzkumníka serveru**, vyberte **připojit k databázi** tlačítko.

2.  V **přidat připojení** dialogovém okně zadejte následující informace:

    -   **Zdroj dat**: `Microsoft SQL Server (SqlClient)`

    -   **Název serveru**:

        -   Chcete-li použít výchozí verzi: `(localdb)\MSSQLLocalDB`.  To určí ProjectV12 nebo ProjectV13, v závislosti na tom, která verze sady Visual Studio je nainstalovaná a vytvoření první instanci LocalDB. **MSSQLLocalDB** uzel v **Průzkumník objektů systému SQL Server** ukazuje, která verze bude ukazovat.

        -   Chcete-li použít konkrétní verzi: `(localdb)\ProjectsV12` nebo `(localdb)\ProjectsV13`, kde je V12 LocalDB 2014 a V13 je LocalDB 2016.

    -   **Připojit soubor databáze**: Fyzická cesta primární *.mdf* souboru.

    -   **Logický název**: Název, který chcete použít se souborem.

3.  Vyberte tlačítko **OK**.

4.  Po zobrazení výzvy, vyberte **Ano** tlačítko Upgradovat soubor.

    Databáze se upgraduje, je připojen k modulu databáze LocalDB a již není kompatibilní s starší verzi LocalDB.

Můžete také upravit připojení SQL Server Express LocalDB použít tak, že otevřete místní nabídku pro připojení a pak vyberete **změna připojení**. V **změna připojení** dialogové okno pole, změňte název serveru, aby `(LocalDB)\MSSQLLocalDB`. V **Upřesnit vlastnosti** dialogové okno pole, ujistěte se, že **uživatelskou instanci** je nastavena na **False**.

### <a name="to-upgrade-a-database-file-to-use-the-sql-server-express-version"></a>Upgrade databázového souboru chcete používat verzi SQL Server Express

1.  V místní nabídce pro připojení k databázi, vyberte **změna připojení**.

2.  V **změna připojení** dialogové okno, vyberte **Upřesnit** tlačítko.

3.  V **Upřesnit vlastnosti** dialogové okno, vyberte **OK** tlačítko beze změny názvu serveru.

    Soubor databáze se upgraduje na shodovat s aktuální verzí systému SQL Server Express.

### <a name="to-work-with-the-database-in-visual-studio-but-retain-compatibility-with-sql-server-express"></a>K práci s databází v sadě Visual Studio, ale zachovat kompatibilitu s SQL Server Express

-   V sadě Visual Studio otevřete projekt bez upgradu ho.

    -   Chcete-li spustit projekt, vyberte **F5** klíč.

    -   Chcete-li upravit databázi, otevřete *.mdf* ve **Průzkumníka řešení**a rozbalte uzel v **Průzkumníka serveru** pro práci s databází.

### <a name="to-make-sql-server-express-the-default-database-engine"></a>Chcete-li systém SQL Server Express výchozí databázový stroj

1.  Na panelu nabídek vyberte **nástroje** > **možnosti**.

2.  V **možnosti** dialogového okna rozbalte **databázové nástroje** možnosti a pak vyberte **datová připojení**.

3.  V **název Instance systému SQL Server** textové pole, zadejte název instance systému SQL Server Express nebo LocalDB, který chcete použít. Pokud není název instance, zadejte `.\SQLEXPRESS or (LocalDB)\MSSQLLocalDB`.

4.  Vyberte tlačítko **OK**.

    SQL Server Express budou mít výchozí databázový stroj pro vaše aplikace.

## <a name="see-also"></a>Viz také:

- [Přístup k datům v sadě Visual Studio](accessing-data-in-visual-studio.md)