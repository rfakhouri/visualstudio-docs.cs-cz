---
title: Přehled rozšíření Visual Studio otevřít složku | Dokumentace Microsoftu
ms.date: 02/21/2018
ms.topic: conceptual
ms.assetid: 94c3f8bf-1de3-40ea-aded-7f40c4b314c7
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 2bb74703f639848d643f536edf620e30b1836310
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806446"
---
# <a name="open-folder-extensibility"></a>Otevřete složku rozšíření

[Otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) funkce umožňuje uživatelům otevírat libovolného základního kódu v sadě Visual Studio bez nutnosti soubory projektu nebo řešení. Otevřít složku poskytuje že funkce uživatelé očekávají ze sady Visual Studio jako například:

* Integrace Průzkumníka řešení a vyhledávání
* Zabarvení editoru
* Přejít na navigace
* Najít v souborech vyhledávání

Při použití úlohy pro vývoj pro .NET a C++, uživatelům se taky získat:

* Rich Intellisense
* Funkce specifické pro jazyk

Autoři rozšíření otevřenou složku můžou vytvářet bohaté funkce pro libovolný jazyk. Nejsou k dispozici rozhraní API pro podporu vytváření, ladění a hledání symbolu pro každý soubor v uživatel základu kódu. Aktuální zařízení Extender můžete aktualizovat svoje existující funkce sady Visual Studio k pochopení kódu bez pomocného projektů nebo řešení.

## <a name="an-api-without-project-systems"></a>Rozhraní API bez systémů projektů

Visual Studio v minulosti rozumí pouze soubory v řešení a jeho projektů s použitím systémů projektů. Systém projektu je zodpovědná za funkce a uživatelské interakce načtený žádný spustitelný projekt. To rozumí co soubory svůj projekt obsahuje vizuální reprezentace obsahu projektu, závislosti na jiných projektech a úpravy základního souboru projektu. Je to prostřednictvím těchto hierarchií a možnosti, které součásti fungovat jménem uživatele. Ne všechny základů kódu jsou dobře reprezentovány ve struktuře projektu a řešení. Skriptovací jazyky a open source kódu napsaného v jazyce C++ pro Linux jsou dobré příklady. Pomocí otevřít složku sady Visual Studio poskytuje uživatelům nový způsob interakce s jejich zdrojový kód.

Rozhraní API, otevřete složku jsou v části `Microsoft.VisualStudio.Workspace.*` obor názvů a jsou k dispozici pro zařízení Extender vytvářet a využívat data nebo akce kolem soubory v rámci funkce Otevřít složku. Rozšíření můžete pomocí těchto rozhraní API poskytuje funkce pro řadu oblastí, včetně:

- [Pracovní prostory](workspaces.md) – od bodu otevřít složku rozšíření je pracovní prostor a jeho rozhraní API.
- [Soubor kontextů a akce](workspace-file-contexts.md) -souboru konkrétního kódu intelligence zajišťována kontexty souborů.
- [Indexování](workspace-indexing.md) – shromažďuje a trvalé uchování dat o pracovních prostorech otevřít složku.
- [Jazykové služby](workspace-language-services.md) – integrace jazykových služeb do pracovních prostorů otevřít složku.
- [Sestavení](workspace-build.md) – podpora pro pracovní prostory otevřít složku sestavení.

Funkce, které používají následující typy muset přijmout nová rozhraní API pro podporu funkce Otevřít složku:

- `IVsHierarchy`
- `IVsProject`
- `DTE`

## <a name="feedback-comments-issues"></a>Zpětná vazba, komentáře, problémy

Otevřete složku a `Microsoft.VisualStudio.Workspace.*` rozhraní API se aktivně vyvíjí. Pokud se zobrazí neočekávané chování, přejděte na téma známé problémy pro vydanou verzi, které vás zajímají. [Komunita vývojářů](https://developercommunity.visualstudio.com) je doporučený místem, kde můžete hlasovat a vytvořte nějaké problémy. Pro každý zpětnou vazbu důrazně doporučujeme podrobný popis problému. Zahrnout verzi sady Visual Studio, kterou vyvíjíte pro, rozhraní API používáte (co jsme implementovali a při interakci s), očekávaný výsledek a skutečným výsledkem. Pokud je to možné zahrnují výpisu proces devenv.exe. Pomocí sledování pro poskytování zpětné vazby na tento problém Githubu a související dokumentaci.

## <a name="next-steps"></a>Další kroky

* [Pracovní prostory](workspaces.md) – Další informace o pracovním prostoru otevřít složku rozhraní API.