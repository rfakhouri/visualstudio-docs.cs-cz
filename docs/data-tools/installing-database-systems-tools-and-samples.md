---
title: "Databáze Kompatibilita sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- database systems
- database compatibility
- databases for Visual Studio
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 8fbe818e233c8bbdaf4431c70b8962baf43a2ed2
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="compatible-database-systems-for-visual-studio"></a>Databázi kompatibilní se systémy pro sadu Visual Studio

K vývoji aplikací dat připojené v sadě Visual Studio, obvykle instalace systému databáze na místním vývojovém počítači a pak nasadit aplikace a databáze v produkčním prostředí Jakmile jsou připravené. Visual Studio nainstaluje SQL Server Express LocalDB na váš počítač jako součást **úložiště dat a zpracování** zatížení. Tuto instanci LocalDB je užitečné pro vývoj aplikací připojení dat, snadno a rychle.

Pro systém databáze byla přístupná z aplikace .NET a mají být zobrazeny v sadě Visual Studio data nástroje windows musí mít zprostředkovatel ADO.NET data provider. Zprostředkovatel musí podporovat rozhraní Entity Framework konkrétně, pokud budete chtít použít Entity datových modelech v aplikaci .NET. Mnoho poskytovatelů jsou nabízena prostřednictvím Správce balíčků NuGet nebo prostřednictvím Visual Studio Marketplace.

Pokud používáte rozhraní API úložiště Azure, nainstalujte emulátorů úložiště Azure na místním počítači během vývoje aby se zabránilo poplatky, dokud nebudete připraveni k nasazení do produkčního prostředí. Další informace najdete v tématu [použití emulátoru úložiště Azure pro vývoj a testování](/azure/storage/common/storage-use-emulator).

Následující seznam obsahuje některé z oblíbenější systémů databáze, které lze použít v projektech Visual Studio. Seznam není vyčerpávající. Seznam jiných dodavatelů, které nabízí zprostředkovatelé dat ADO.NET, které umožňují těsná integrace s nástroji Visual Studio najdete v tématu [zprostředkovatele dat ADO.NET](/dotnet/framework/data/adonet/data-providers).

## <a name="microsoft-sql-server"></a>Microsoft SQL Server

SQL Server je databáze nejdůležitějšího Microsoft nabídky. SQL Server 2016 poskytuje revoluční výkon, pokročilé zabezpečení a bohaté, integrované sestavy a analýzy. Je dodáván v různých edicích, které jsou určené pro jiné účely: z pro použití v jednom počítači vysoce škálovatelnou a vysoce výkonné obchodní analýzy. SQL Server Express je plnohodnotný edice systému SQL Server, který je přizpůsobený pro opětovnou distribuci a vložení.  LocalDB je zjednodušená edice systému SQL Server Express, která vyžaduje žádná konfigurace a běží v procesu vaší aplikace. Můžete si stáhnout nebo oba produkty z [SQL Server Express stránky pro stažení](https://www.microsoft.com/sql-server/sql-server-editions-express). Mnoho příkladů SQL v této části použijte SQL Server LocalDB. SQL Server Management Studio (SSMS) je samostatná databáze správy aplikace, která má více funkcí než je zadán v Průzkumníku objektů Server SQL sady Visual Studio. Aplikace SSMS můžete získat z předchozích odkazu.

## <a name="oracle"></a>Oracle

Si můžete stáhnout na placené nebo bezplatnou verzi z databáze Oracle [síťové technologie Oracle](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html) stránky. Pro podporu rozhraní Entity Framework a TableAdapters návrhu, budete potřebovat [Oracle Developer Tools pro sadu Visual Studio](http://www.oracle.com/technetwork/developer-tools/visual-studio/overview/index.html). Další oficiální Oracle produkty, včetně Oracle rychlých klienta, jsou k dispozici prostřednictvím Správce balíčků NuGet.  Ukázka schémata Oracle si můžete stáhnout podle pokynů v [Online dokumentaci Oracle](http://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm).

## <a name="mysql"></a>MySQL

MySQL je systém oblíbených open-source databáze, který se často používá v podnicích a weby. Stahování pro databázi MySQL, MySQL pro Visual Studio a souvisejících produktů je v [MySQL v systému Windows](http://www.mysql.com/why-mysql/windows/).  Třetí strany nabízejí různé rozšíření Visual Studia a samostatné správy aplikací pro databázi MySQL. Můžete procházet nabídek Správce balíčků NuGet (**nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet pro řešení**) .

## <a name="postgresql"></a>PostgreSQL

PostgreSQL je relační databázový systém volné, open-source objektu. Chcete-li jej nainstalovat na Windows, můžete stáhnout z [stránky pro stažení PostgreSQL](http://www.postgresql.org/download/windows/).  Můžete také vytvořit PostgreSQL ze zdrojového kódu.  Systém jádra PostgreSQL obsahuje rozhraní jazyka C. Mnoho třetím stranám uveďte balíčky NuGet pro používání PostgreSQL z aplikací .NET.  Můžete procházet nabídek Správce balíčků NuGet (**nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet pro řešení**) . Možná je poskytovaný balíček nejoblíbenější [npgsql.org](http://www.npgsql.org).

## <a name="sqlite"></a>SQLite

SQLite je vložený databázový stroj SQL, který běží v procesu aplikace vlastní. Si můžete stáhnout z [stránky pro stažení SQLite](http://www.sqlite.org/download.html). Mnoho balíčky NuGet třetích stran pro SQLite jsou k dispozici. Můžete procházet nabídek Správce balíčků NuGet (**nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet pro řešení**) .

## <a name="firebird"></a>Firebird

Firebird je systém, databáze SQL open source. Si můžete stáhnout z [stránky pro stažení Firebird](http://firebirdsql.org/en/downloads/). Zprostředkovatel ADO.NET data provider je k dispozici prostřednictvím Správce balíčků NuGet.

## <a name="see-also"></a>Viz také

[Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)  
[Jak určit verzi a edici systému SQL Server a jeho komponenty](http://support.microsoft.com/kb/321185)