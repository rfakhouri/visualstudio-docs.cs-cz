---
title: "Výběr a instalace překladače Python | Microsoft Docs"
description: "Úplný seznam překladače Python, které jsou podporovány v sadě Visual Studio s stručné pokyny k vyhledávání jejich instalační programy."
ms.custom: 
ms.date: 02/20/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 1bdec69c45cbd6ebb7943ce38853fd2207000a0f
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="installing-python-interpreters"></a>Instalace překladače Python

Ve výchozím nastavení instalaci zatížení vývoj Python ve Visual Studio 2017 se nainstaluje také Python 3 (64 bitů). Volitelně můžete pro instalaci 32bitové a 64bitové verze Python 2, Python 3, Anaconda 2 a Anaconda 3, jak je popsáno v [instalace](installing-python-support-in-visual-studio.md).

Můžete také ručně nainstalovat všechny překladače uvedené v následující tabulce mimo instalační program sady Visual Studio. Například pokud jste nainstalovali Anaconda 3 před instalací sady Visual Studio, nemusíte jej znovu nainstalujte pomocí instalačního programu sady Visual Studio.

Pro Visual Studio 2015 a starší je nutné mezi překladače nainstalovat ručně.

Visual Studio (všechny verze) automaticky rozpozná všechny nainstalované překladač Pythonu a jeho prostředí kontrolou registru (následující [období 514 - Python registrace v registru Windows](https://www.python.org/dev/peps/pep-0514/)).

Pokud Visual Studio nerozpozná nainstalované prostředí, přečtěte si téma [ručně Identifikace stávajícího prostředí](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

Zobrazuje všechny známé prostředí v sadě Visual Studio [okno prostředí Python](managing-python-environments-in-visual-studio.md)a automaticky zjišťuje aktualizace stávající překladače.

| Překladač | Popis |
| --- | --- |
| [CPython](https://www.python.org/) | "Nativní" a nejčastěji používaných překladač, k dispozici v 32bitové a 64bitové verze (32bitová verze doporučené). Zahrnuje nejnovější funkce jazyka, maximální kompatibility balíček Python, plná podpora ladění a interoperabilita s [IPython](http://ipython.org/). Viz také: [použít Python 2 nebo Python 3?](http://wiki.python.org/moin/Python2orPython3). Všimněte si, že Visual Studio 2015 a starší nepodporují Python 3.6 a může poskytnout chyba "Unsupported verze python 3.6". Používat jazyk Python, 3.5 nebo starší místo. |
| [IronPython](https://github.com/IronLanguages/ironpython2) | Implementace rozhraní .NET jazyka Python, k dispozici v 32bitové a 64bitové verze, C# / f # nebo Visual Basic zprostředkovatel komunikace s objekty, poskytuje přístup k rozhraní API technologie .NET, standardní Python ladění (ale ne C++ ve smíšeném režimu ladění) a ve smíšeném IronPython / C# ladění. IronPython, ale nepodporuje virtuální prostředí. |
| [Anaconda](https://www.continuum.io) | Platformě vědecké účely open data používá technologii Python a obsahuje nejnovější verzi CPython a většina těžko instalovat balíčky. Doporučujeme, abyste ho nelze v opačném případě rozhodnete-li. |
| [PyPy](http://www.pypy.org/) | Vysoce výkonné trasování JIT, provádění Python, který je vhodný pro dlouhodobé programy a situacích slouží k určení výkonu problémy, ale nemůže najít jiné řešení. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |
| [Jython](http://www.jython.org/) | Implementace jazyka Python na virtuální počítač Java (JVM). Podobá se IronPython, kód spuštěný v Jython mohou komunikovat s třídy jazyka Java a knihovny, ale nemusí být možné používat mnoho knihovny určené pro CPython. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |

Vývojáři, které chcete přidat nové formuláře detekce prostředí Python, zobrazit [PTVS prostředí detekce](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (webu github.com).

## <a name="moving-an-interpreter"></a>Přesunutí překladač

Pokud přesouváte existující překladač do nového umístění pomocí systému souborů, Visual Studio nerozpozná automaticky změnu.

- Pokud jste původně zadali umístění překladač prostřednictvím **prostředí Python** okno, upravit jeho prostředí pomocí **konfigurace** kartě v okně pro určení nového umístění. V tématu [ručně Identifikace stávajícího prostředí](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

- Pokud jste nainstalovali překladač pomocí instalačního programu, použijte následující postup k opětovné instalaci překladač v novém umístění:

  1. Překladač Pythonu obnovte do původního umístění.
  2. Odinstalujte překladač pomocí jeho instalačního programu, který vymaže položky registru.
  3. Přeinstalujte překladač v požadovaném umístění.
  4. Restartujte Visual Studio, který by měl automaticky rozpoznat nové umístění místo původního umístění.

Následující tento proces zajišťuje, že jsou správně aktualizovat položky registru, které identifikují překladač na umístění, které používá Visual Studio. Pomocí instalačního programu také obstará žádné vedlejší účinky, které mohou existovat.

## <a name="see-also"></a>Viz také

- [Správa prostředí Python](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)