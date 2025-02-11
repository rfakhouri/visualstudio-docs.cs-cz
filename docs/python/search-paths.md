---
title: Použití Pythonu cesty pro hledání
description: Visual Studio nabízí že další specifické prostředky k určení vyhledávací cesty pro projekty do neměli používat proměnné celý systém a prostředí.
ms.date: 03/13/2019
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 37ce9d7b1853dfecc9e0ec33ca08c3c3fa0571e0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62428426"
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Jak sada Visual Studio používá Python cesty pro hledání

S typickému využití Python `PYTHONPATH` proměnné prostředí (nebo `IRONPYTHONPATH`atd) poskytuje výchozí cesta pro vyhledávání souborů modulu. To znamená, když použijete `from <name> import...` nebo `import <name>` příkaz Python prohledává v pořadí pro odpovídající název následujících umístění:

1. Integrované moduly v Pythonu.
1. Složka obsahuje kód Pythonu, který používáte.
1. "Modul cesty pro hledání" jako určené proměnnou prostředí použít. (Naleznete v tématu [The cesty pro hledání modulu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) a [proměnné prostředí](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) v samotném dokumentace pro Python.)

Visual Studio ignoruje proměnné prostředí path v hledání, ale i v případě, že proměnná je nastavena pro celý systém. Je ignorována, ve skutečnosti, přesně *protože* nastavit pro celý systém a tedy vyvolává některé otázky, které nejde automaticky odpovědi: Jsou odkazovaná moduly určené pro Python 2.7 nebo Python 3.6 +? Budou se přepsat standardní knihovny moduly? Vývojář si je vědoma toto chování nebo je pokus o zneužití škodlivým?

Visual Studio tak poskytuje prostředky ke specifikaci cesty pro hledání přímo v prostředí a projekty. Kód, který můžete spustit nebo ladit v sadě Visual Studio přijímá cesty pro hledání v hodnotě `PYTHONPATH` (a další ekvivalentní proměnné). Přidáním cesty pro hledání sady Visual Studio zkontroluje knihovny v těchto umístěních a sestavuje databáze IntelliSense pro ně v případě potřeby (Visual Studio 2017 verze 15.5 a starší; vytváření databáze může chvíli trvat v závislosti na počtu knihovny).

Přidání cesty pro hledání, přejděte na **Průzkumníka řešení**, rozbalte uzel projektu, klikněte pravým tlačítkem na **cesty pro hledání**vyberte **přidat složku do cesty pro hledání**:

::: moniker range="vs-2017"
![Přidat složku do cesty pro hledání příkaz na cesty pro hledání v Průzkumníkovi řešení](media/search-paths-command.png)
::: moniker-end
::: moniker range=">=vs-2019"
![Přidat složku do cesty pro hledání příkaz na cesty pro hledání v Průzkumníkovi řešení](media/search-paths-command-2019.png)
::: moniker-end

Tento příkaz zobrazí prohlížeč, ve kterém pak vyberte složku, kterou chcete zahrnout.

Pokud vaše `PYTHONPATH` již obsahuje složky chcete, aby proměnné prostředí, použijte **přidat PYTHONPATH cesty pro hledání** jako praktický zástupce.

Jakmile složky jsou přidány do cesty hledání, Visual Studio používá tyto cesty pro jakékoli prostředí spojené s projektem. (Může se zobrazit chyby Pokud prostředí je založená na jazyce Python 3 a pokuste se přidat cesty pro hledání na moduly Pythonu 2.7.)

Soubory s *ZIP* nebo *.egg* rozšíření můžete také přidat jako cesty pro hledání tak, že vyberete **přidat archiv Zip do cesty pro hledání** příkazu. Stejně jako u složky, jsou obsah těchto souborů zkontrolovaných a k dispozici pro technologii IntelliSense.

## <a name="see-also"></a>Viz také:

- [Správa prostředí Pythonu v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Odkaz na okno prostředí Pythonu](python-environments-window-tab-reference.md)
