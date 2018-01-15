---
title: "Kód generování funkce v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/11/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 7740fcea4ac944242f4284382cf26544d9ea95b5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="code-generation-features-in-visual-studio"></a>Funkce generování kódu v sadě Visual Studio

Existuje mnoho způsobů tak, aby měl generovat kód pro vás v editoru Visual Studio. Pomocí těchto funkcí generování kódu můžete ušetřit čas a stisknutí kláves, snížit počet chyb syntaxe a zlepšit konzistence napříč vašeho kódu.

Některé funkce v sadě Visual Studio, které generují kód pro zahrnete [výstřižky kódu](../ide/code-snippets.md) a [rychlé akce](../ide/quick-actions.md) ![malé ikonou žárovky](media/vs2015_lightbulbsmall.png).

Některé běžné kódu generování úlohy k dispozici prostřednictvím [rychlé akce](../ide/quick-actions.md) jsou:

* Generování tříd, metod, vlastností, atd.

* Implementace rozhraní nebo abstraktní třídy

* Úvod do složitý výraz místní proměnné

Zadáním určitých znaků můžete navíc:

* Generovat [formátu XML komentář bloky]() pro váš kód, který lze později zpracovat k vytvoření dokumentace automaticky

* Generovat [přepsání metody]() podpisy

Protože logiku generování kódu úzce souvisí syntaxe jazyka, každý služba jazyka v sadě Visual Studio poskytuje možnosti generování vlastní kód.

## <a name="see-also"></a>Viz také

[Rychlé akce](../ide/quick-actions.md)  
[Fragmenty kódu](../ide/code-snippets.md)  
[Vytvoření kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md)  
[Refactoring](../ide/refactoring-in-visual-studio.md)