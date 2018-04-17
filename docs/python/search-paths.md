---
title: Jak se používají cesty pro hledání Python
description: Přehled používání Python cesty hledání v prostředí a projektů v sadě Visual Studio.
ms.custom: ''
ms.date: 03/05/2018
ms.technology:
- devlang-python
ms.devlang: python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 22e28431d22229e6096dc05d21decd88c3d0782d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Používání cesty pro hledání Python v sadě Visual Studio

S typickému využití Python `PYTHONPATH` proměnnou prostředí (nebo `IRONPYTHONPATH`atd) poskytuje výchozí cesta hledání pro soubory modulu. To znamená, když použijete `from <name> import...` nebo `import <name>` prohlášení, Python prohledává v pořadí pro odpovídajícím názvem následujících umístěních:

1. Integrované moduly jazyka Python.
1. Složka obsahující kód Python, které používáte.
1. "Modul vyhledávání cestu" jako definovanou proměnnou prostředí použít. (V tématu [Path hledání modulu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) a [proměnné prostředí](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) v základní dokumentace Python.)

Visual Studio ignoruje proměnné prostředí path hledání, ale i v případě, že proměnná je nastavená pro celý systém. Je ignorován ve skutečnosti, přesněji *protože* je nastavena pro celý systém a proto vyvolá určité otázek, které nelze automaticky zodpovězeny: odkazovaný moduly, které jsou určené výhradně pro Python 2.7 nebo Python 3.6? Budou se přepsat standardní knihovna moduly? Vývojář si je vědoma toto chování nebo je škodlivý zneužití pokus?

Visual Studio tak poskytuje i prostředky ke specifikaci cest hledání přímo v prostředí a projekty. Kód, který můžete spustit nebo ladění v sadě Visual Studio obdrží cesty hledání v hodnotě `PYTHONPATH` (a ostatní ekvivalentní proměnné). Přidáním cesty hledání Visual Studio zkontroluje knihovny v těchto umístěních a vytvoří databáze IntelliSense pro ně v případě potřeby (Visual Studio 2017 verze 15,5 a starší; vytváření databáze může chvíli trvat v závislosti na počtu knihovny).

Chcete-li přidat cestu vyhledávání, klikněte pravým tlačítkem na **cesty hledání** položky v Průzkumníku řešení, vyberte **přidat složku do cesty pro hledání...** a vyberte složku, kterou chcete zahrnout. Tato cesta je používána pro jakékoli prostředí přidružený k projektu. (Může se zobrazit chyby Pokud prostředí je založena na Python 3 a pokusíte se do přidat cestu vyhledávání modulů Python 2.7.)

Soubory s `.zip` nebo `.egg` rozšíření lze také přidat jako cesty hledání tak, že vyberete **přidat archivu Zip do cesty pro hledání...** . Stejně jako u složky, obsah tyto soubory jsou kontrolovány a k dispozici pro technologii IntelliSense.

Pokud používáte pravidelně stejné cesty pro hledání a obsah se často nemění, může být efektivnější k její instalaci do vaší lokality balíčky složky. Cesta hledání se pak analyzují a uloženy v databázi IntelliSense, je vždycky být přidružen prostředí určený a nevyžaduje cesta hledání mají být přidány do každého projektu.

## <a name="see-also"></a>Viz také

- [Správa prostředí Python v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)