---
title: "IntelliSense pro R kód v sadě Visual Studio | Microsoft Docs"
description: "Visual Studio IntelliSense zobrazí informace o funkcích, členové objektu, fragmenty kódu a dokončování operací při psaní kódu jazyka R."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 18b65727f387bf69688bd605ce4d390972a5ed73
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="intellisense"></a>IntelliSense

Visual Studio IntelliSense zobrazí informace o funkcích, které bude možné volat, členové objektů argumenty funkce a [výstřižky kódu](code-snippets-for-r.md) přímo v zobrazení jako můžete napsat kód. Také zobrazuje možná dokončení při psaní a se dokončí po stisknutí klávesy Enter nebo kartě (najdete v části [možností editoru](editing-r-code-in-visual-studio.md#editor-options) pro **Upřesnit** karta). Je k dispozici v obou editoru IntelliSense a [interaktivních okna](interactive-repl-for-r-in-visual-studio.md).

![IntelliSense zobrazující podpis funkce](media/intellisense-function-signature.png)

Při psaní funkce nebo další příkaz, IntelliSense poskytuje automatické dokončování nabídky (case-sensitively) Filtroval co jste už zadali:

![Nabídky Automatické dokončování IntelliSense](media/intellisense-auto-complete-menu.png)

Klávesy Tab (nebo zadejte nebo místo, v závislosti na tom, jak jsou nastavené možnosti), vloží položce vybrané v rozevírací nabídce. Výběr můžete změnit pomocí klávesy se šipkami.

Technologie IntelliSense také nabízí návrhy pro členy R objektů:

![Návrhy IntelliSense pro členy objektu](media/intellisense-auto-complete-r-objects.png)

V nabídce stisknutím klávesy ESC zcela zavře. Můžete jej zahrnout zálohování pomocí kombinace kláves Ctrl + mezerník.

Zadáním otevření `(` pro funkci vloží volání zavření `)` a vyvoláte nápovědy podpisu, jako je uvedené výše:

![Nápověda podpis technologie IntelliSense pro funkci](media/intellisense-function-signature.png)

Znovu ESC zavře místní; Funkce signatury lze provést ho znovu pomocí kombinace kláves Ctrl + Shift + mezerník.

> [!Tip]
> Pokud parametr nápovědy skryje text pod ním, stiskněte a podržte klávesu Ctrl, chcete-li parametr průhledná text nápovědy.

## <a name="intellisense-for-user-defined-functions-and-variables"></a>IntelliSense pro uživatelsky definované funkce a proměnné

IntelliSense platí pro uživatelsky definované funkce ve stejném souboru, včetně dokončení parametr name:

![IntelliSense pro uživatelsky definované funkce](media/intellisense-same-file-functions.png)

![Parametr doplňování IntelliSense pro uživatelsky definované funkce](media/intellisense-parameter-completion.png)

IntelliSense platí také pro proměnných ve stejném souboru a aktuální relace:

![Proměnné doplňování IntelliSense](media/intellisense-variable-completion.png)

> [!Note]
> V okně interaktivní IntelliSense považovat jenom názvy v aktuální relaci R a ignoruje soubory v projektu.

## <a name="code-suggestions"></a>Návrhy kódu

Visual Studio žárovky (nazývané inteligentních značek) se zobrazí v okraj, je které naznačují, že je k dispozici pro běžně používané akce zástupce. Například najeďte myší na řádek, který obsahuje `library` příkaz v editoru zobrazíte žárovky. Výběr žárovky zobrazí dostupné možnosti:

![Inteligentní značky pro R v editoru](media/intellisense-smart-tags.png)
