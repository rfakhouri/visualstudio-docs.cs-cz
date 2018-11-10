---
title: Použití Pythonu cesty pro hledání
description: Přehled použití cesty hledání Pythonu v prostředí a projekty v sadě Visual Studio.
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 92185b224af50dd5cf125d62282f1e8f7b951bc6
ms.sourcegitcommit: bc43970c000f07c9cc2051f1264a9742943a9755
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2018
ms.locfileid: "51348992"
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Jak sada Visual Studio používá Python cesty pro hledání

S typickému využití Python `PYTHONPATH` proměnné prostředí (nebo `IRONPYTHONPATH`atd) poskytuje výchozí cesta pro vyhledávání souborů modulu. To znamená, když použijete `from <name> import...` nebo `import <name>` příkaz Python prohledává v pořadí pro odpovídající název následujících umístění:

1. Integrované moduly v Pythonu.
1. Složka obsahuje kód Pythonu, který používáte.
1. "Modul cesty pro hledání" jako určené proměnnou prostředí použít. (Naleznete v tématu [The cesty pro hledání modulu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) a [proměnné prostředí](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) v samotném dokumentace pro Python.)

Visual Studio ignoruje proměnné prostředí path v hledání, ale i v případě, že proměnná je nastavena pro celý systém. Je ignorována, ve skutečnosti, přesně *protože* nastavit pro celý systém a tedy vyvolává některé otázky, které nejde automaticky odpovědi: jsou odkazovaná moduly určená pro Python 2.7 nebo Python 3.6 +? Budou se přepsat standardní knihovny moduly? Vývojář si je vědoma toto chování nebo je pokus o zneužití škodlivým?

Visual Studio tak poskytuje prostředky ke specifikaci cesty pro hledání přímo v prostředí a projekty. Kód, který můžete spustit nebo ladit v sadě Visual Studio přijímá cesty pro hledání v hodnotě `PYTHONPATH` (a další ekvivalentní proměnné). Přidáním cesty pro hledání sady Visual Studio zkontroluje knihovny v těchto umístěních a sestavuje databáze IntelliSense pro ně v případě potřeby (Visual Studio 2017 verze 15.5 a starší; vytváření databáze může chvíli trvat v závislosti na počtu knihovny).

Přidání cesty pro hledání, klikněte pravým tlačítkem na **cesty pro hledání** položky v **Průzkumníka řešení**vyberte **přidat složku do cesty pro hledání**a vyberte složku, kterou chcete zahrnout. Tato cesta se používá pro všechny prostředí spojené s projektem. (Může se zobrazit chyby Pokud prostředí je založená na jazyce Python 3 a pokuste se přidat cesty pro hledání na moduly Pythonu 2.7.)

Soubory s *ZIP* nebo *.egg* rozšíření můžete také přidat jako cesty pro hledání tak, že vyberete **přidat archiv Zip do cesty pro hledání**. Stejně jako u složky, jsou obsah těchto souborů zkontrolovaných a k dispozici pro technologii IntelliSense.

Pokud jsou pravidelně pomocí stejné vyhledávací cesty a obsah se často nemění, může být efektivnější k její instalaci do složky balíčků webů. Cesty pro hledání se pak analyzuje a uloženy v databázi technologie IntelliSense, je vždy přidruženo zamýšleném prostředí a nevyžaduje, aby přidávané do každého projektu cesty pro hledání.

## <a name="see-also"></a>Viz také:

- [Správa prostředí Pythonu v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Odkaz na okno prostředí Pythonu](python-environments-window-tab-reference.md)
