---
title: Refaktoring kódu jazyka Python
description: Jak na snadno refactor Python kódu v sadě Visual Studio přejmenováním identifikátory, extrahování metody, přidávání importech a odebírání nepoužívané importuje.
ms.date: 07/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: bc06ba43261a90dcfe6677a73c8a267a7efdcb1c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="refactoring-python-code"></a>Refaktoring kódu jazyka Python

Visual Studio obsahuje několik příkazů pro automaticky transformaci a čištění vašeho Python zdrojového kódu:

- [Přejmenujte](#rename) přejmenuje vybraná třída, metoda nebo název proměnné
- [Extrahování metody](#extract-method) vytvoří novou metodu z na vybraný úsek kódu
- [Přidat import](#add-import) poskytuje inteligentní značky přidat chybějící importu
- [Odebrat nepoužité importy](#remove-unused-imports) odebere nepoužívané importy

<a name="rename-variable"</a>

## <a name="rename"></a>přejmenování

1. Klikněte pravým tlačítkem na identifikátor chcete přejmenovat a vyberte **přejmenovat**, nebo umístit vsuvka tento identifikátor a vyberte **Upravit > Refaktorovat > přejmenujte...**  příkaz nabídky (F2).
1. V **přejmenovat** dialog, který se zobrazí, zadejte nový název pro identifikátor a vyberte **OK**:

  ![Přejmenujte výzva k zadání nového názvu identifikátor](media/code-refactor-rename-1.png)

1. V dialogovém okně Další vyberte soubory a instance v kódu na kterou budou používány přejmenování; Vyberte všechny jednotlivé instance náhled určité změny:

  ![Přejmenujte dialog, určete, kam se použít změny](media/code-refactor-rename-2.png)

1. Vyberte **použít** provést změny na zdrojové soubory vašeho kódu. (Tato akce může být vrátit zpět.)

## <a name="extract-method"></a>Extrahování metody

1. Vyberte řádky kódu nebo výraz, který se extrahuje do samostatné metodě.
1. Vyberte **Upravit > Refaktorovat > extrahování metody...**  příkaz nabídky nebo typ Ctrl-R, M.
1. V dialogovém okně se zobrazí zadejte nový název metody, ukazují, kde rozbalte ho do a vyberte všechny proměnné uzavření. Není vybrána pro uzavření proměnné jsou převedena na metoda argumenty:

  ![Extrahování dialogu – metoda](media/code-refactor-extract-method-1.png)

1. Vyberte **OK** a kód je upravit odpovídajícím způsobem:

  ![Účinek extrahování metody](media/code-refactor-extract-method-2.png)

## <a name="add-import"></a>Přidat importu

Při umístění pomocí kurzoru na identifikátor informací o chybí typu, Visual Studio poskytuje inteligentní značky (ikona žárovek nalevo od kódu), jehož příkazy přidat nezbytné `import` nebo `from ... import` příkaz:

![Přidání import inteligentní značky](media/code-refactor-add-import-1.png)

Visual Studio nabízí `import` dokončených pro balíčky nejvyšší úrovně a modulů v aktuálním projektu a standardní knihovny. Visual Studio také nabízí `from ... import` dokončených pro submodules a dílčí balíčky a také členové modulu. Dokončování zahrnovat funkce, třídy nebo exportovaná data. Vyberte buď možnost přidá příkaz tak, aby v horní části souboru po další importy, nebo do existující `from ... import` příkaz, pokud modul stejné již byla naimportována.

![Výsledkem přidání importu](media/code-refactor-add-import-2.png)

Visual Studio se pokusí vyfiltrovat členy, kteří nejsou ve skutečnosti definována v modulu, jako jsou moduly, které jsou importovány do jiné, ale nejsou podřízené objekty to import modulu. Například mnoho modulů použít `import sys` místo `from xyz import sys`, takže se nezobrazí dokončení pro import `sys` z ostatních modulů i v případě, že chybí moduly `__all__` člena, který vylučuje `sys`.

Podobně Visual Studio filtruje funkce, které jsou importovány z ostatních modulů nebo předdefinovaný obor názvů. Například pokud modul importuje `settrace` funkce z `sys` modul, pak teoreticky naimportovat jej z tohoto modulu. Je nejvhodnější použít, ale `import settrace from sys` přímo, a proto Visual Studio nabízí tento příkaz konkrétně.

Nakonec, pokud něco by za normálních okolností vyloučeny, ale má jiné hodnoty, které by byly součástí (protože název se přiřazenou hodnotu v modulu, například), Visual Studio stále vyloučí importu. Toto chování se předpokládá, že hodnota by neměla exportovat, protože je definována v jiný modul, a proto je pravděpodobně fiktivní hodnotu, která není taky exportovat další přiřazení.

<a name="remove-imports"</a>

## <a name="remove-unused-imports"></a>Odebrat nepoužité importy

Při psaní kódu, je snadné se `import` příkazy pro moduly, které nejsou používány vůbec. Protože Visual Studio analyzuje kódu, může automaticky zjistit, jestli `import` prohlášení je potřeba pohledem na tom, jestli se používá název importované v rámci oboru níže, kde dochází k příkazu.

Klikněte pravým tlačítkem na libovolné místo v editoru a vyberte **odebrat importy**, což dává možnosti odebrání **všechny obory** nebo právě **aktuální obor**:

![Odebrat importuje nabídky](media/code-refactor-remove-imports-1.png)

Visual Studio pak provede odpovídající změny kódu:

![Účinek odebrání importy](media/code-refactor-remove-imports-2.png)

Všimněte si, že Visual Studio neanalyzuje tok řízení; pomocí názvu před `import` příkaz je zpracován jako ve skutečnosti použit název. Visual Studio také ignoruje všechny `from __future__` importy, importy, které se provádí v definici třídy, také z `from ... import *` příkazy.