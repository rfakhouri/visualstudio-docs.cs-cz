---
title: Databázové projekty a projekty DAC
ms.date: 11/21/2018
ms.topic: conceptual
helpviewer_keywords:
- databases, managing change
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 2a86d9511e470c9a810ff58e80e4cae1f9a0cb11
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55924640"
---
# <a name="database-projects-and-data-tier-applications"></a>Databázové projekty a aplikace datové vrstvy

Databázové projekty můžete vytvářet nové databáze nové aplikace datové vrstvy (DAC) a k aktualizaci stávajících databází a aplikací datové vrstvy. Databázové projekty a projekty DAC umožňují použít verzi ovládacího prvku a projekt správy techniky k vývoji vaší databáze, jako v podstatě stejným způsobem, platí tyto techniky pro spravovaný nebo nativní kód. Může pomoct váš vývojový tým, správou změn databáze a databázové servery vytvořením projektu DAC, databázový projekt nebo Serverový projekt a vložení v rámci správy verzí. Členy týmu můžete pak rezervace souborů provádět, sestavit a otestovat změny v izolované vývojové prostředí, nebo izolovaného prostoru, než je sdílet s týmem. K zajištění kvality kódu, můžete dokončit váš tým a testovat všechny změny pro konkrétní verzi databáze v testovacím prostředí před nasazením změny do produkčního prostředí.

Seznam vlastností databáze, které podporuje aplikace datové vrstvy, naleznete v tématu [podporu objektů systému SQL Server DAC](/sql/relational-databases/data-tier-applications/dac-support-for-sql-server-objects-and-versions). Pokud používáte funkce ve vaší databázi, které nejsou podporované aplikace datové vrstvy, místo toho používejte databázového projektu ke správě změn k vaší databázi.

## <a name="common-high-level-tasks"></a>Běžné úlohy vyšší úrovně

| Základní úlohy | Podpůrný obsah |
| - | - |
| **Zahájení vývoje aplikace datové vrstvy:** Koncept aplikace datové vrstvy (DAC) byla zavedena v systému SQL Server 2008. DAC obsahuje definici pro databázi serveru SQL Server a podpůrné instance objektů, které jsou používány klient server nebo 3vrstvé aplikace. DAC obsahuje databázové objekty, jako jsou tabulky a zobrazení, společně s instanci entity, jako jsou přihlášení. Visual Studio můžete vytvořit projekt DAC, sestavení soubor balíčku DAC a odeslat soubor balíčku DAC správce databáze pro nasazení na instanci databázového stroje systému SQL Server. | - [Aplikace datové vrstvy](/sql/relational-databases/data-tier-applications/data-tier-applications)<br />- [SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms) |
| **Provádění vývoj iterativní databází:** Vývojáři můžou projděte si části projektu a jejich aktualizaci v izolované vývojové prostředí. Pomocí tohoto typu prostředí můžete otestovat provedené změny aniž by to ovlivnilo ostatní členové týmu. Po dokončení se změny, zkontrolujte soubory zpět do správy verzí, kde můžete získat provedené změny a sestavení a nasazení testovacího serveru ostatním členům týmu. | - [Vývoj projektů objektově orientovaný offline databáze (SQL Server Data Tools)](/sql/ssdt/project-oriented-offline-database-development)<br />- [Ladicí program Transact-SQL (SQL Server Management Studio)](/sql/ssms/scripting/transact-sql-debugger) |
| **Vytváření prototypů ověřování výsledků testů a úpravy databázové skripty a objekty:** Editor jazyka Transact-SQL můžete použít k provádění kterékoli z těchto běžných úkolů. | - [Editory dotazu a text (SQL Server Management Studio)](/sql/ssms/scripting/query-and-text-editors-sql-server-management-studio) |

## <a name="see-also"></a>Viz také:

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)