---
title: Databázové projekty, server projekty a projekty DAC v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7f3d3f8dc34cf354fd6cb6b6689701dab791132d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942527"
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>Databázové projekty a aplikace datové vrstvy v sadě Visual Studio

Databázové projekty můžete vytvářet nové databáze nové aplikace datové vrstvy (DAC) a k aktualizaci stávajících databází a aplikací datové vrstvy. Databázové projekty a projekty DAC umožňují použít verzi ovládacího prvku a projekt správy techniky k vývoji vaší databáze, jako v podstatě stejným způsobem, platí tyto techniky pro spravovaný nebo nativní kód. Může pomoct váš vývojový tým, správou změn databáze a databázové servery vytvořením projektu DAC, databázový projekt nebo Serverový projekt a vložení v rámci správy verzí. Členy týmu můžete pak rezervace souborů provádět, sestavit a otestovat změny v izolované vývojové prostředí, nebo izolovaného prostoru, než je sdílet s týmem. K zajištění kvality kódu, můžete dokončit váš tým a testovat všechny změny pro konkrétní verzi databáze v testovacím prostředí před nasazením změny do produkčního prostředí.

Seznam vlastností databáze, které podporuje aplikace datové vrstvy, naleznete v tématu [funkce podporovány v aplikace datové vrstvy](/previous-versions/visualstudio/visual-studio-2010/ee362013(v=vs.100)). Pokud používáte funkce ve vaší databázi, které nejsou podporované aplikace datové vrstvy, místo toho používejte databázového projektu ke správě změn k vaší databázi.

## <a name="common-high-level-tasks"></a>Běžné úlohy vyšší úrovně

| Základní úlohy | Podpůrný obsah |
| - | - |
| **Spuštění vývoje aplikace datové vrstvy:** A DAC je nový koncept nepředchází [!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)] , který obsahuje definici pro [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databázi a podpůrné instance objektů, které jsou používány klient server nebo vrstvy 3 aplikace. DAC obsahuje databázové objekty, jako jsou tabulky a zobrazení, společně s instanci entity, jako jsou přihlášení. Můžete použít Visual Studio vytvořte projekt DAC sestavení souboru DAC balíček a odeslat tento soubor balíčku DAC správce databáze pro nasazení do instance [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databázového stroje. | -   [Vytváření a Správa aplikace datové vrstvy](http://go.microsoft.com/fwlink/?LinkId=160741)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328) |
| **Provádění databáze iterativní vývoj:** Pokud jste vývojář nebo tester, projděte si části projektu a potom je aktualizovat v izolované vývojové prostředí. Pomocí tohoto typu prostředí můžete otestovat provedené změny aniž by to ovlivnilo ostatní členové týmu. Po dokončení se změny, zkontrolujte soubory zpět do správy verzí, kde můžete získat provedené změny a sestavení a nasazení testovacího serveru ostatním členům týmu. | -   [Dotaz a textových editorů (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327)<br />-   [Ladicí program Transact-SQL](http://go.microsoft.com/fwlink/?LinkId=227324) |
| **Vytváření prototypů, ověření výsledcích testu a změny databáze skripty a objekty:** můžete použít [!INCLUDE[tsql](../data-tools/includes/tsql_md.md)] editor k provádění kterékoli z těchto běžných úkolů. | -   [Dotaz a textových editorů (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) |

## <a name="see-also"></a>Viz také:

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
