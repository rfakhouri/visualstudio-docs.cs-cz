---
title: Možnosti, textový Editor, C/C++ experimentální
ms.date: 08/02/2017
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
author: mikeblome
ms.author: mblome
manager: wpickett
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- cplusplus
ms.openlocfilehash: 6ddb535a61b654297c8b7d93ac13e1161725d769
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234631"
---
# <a name="options-text-editor-cc-experimental"></a>Možnosti, textový Editor, C/C++ experimentální

Změníte-li tyto možnosti, můžete změnit chování související s IntelliSense a procházení databáze, když jste programování v C nebo C++. Tyto funkce jsou skutečně experimentální a může být upravena nebo v budoucí verzi odebrána ze sady Visual Studio. Toto téma popisuje možnosti v nástroji Visual Studio 2017. Visual Studio 2015, najdete v části [možnosti, textový Editor, C/C++, experimentální](https://msdn.microsoft.com/library/mt591979.aspx)

Chcete-li získat přístup k této stránky vlastností, stiskněte **CTRL + Q** aktivovat `Quick Launch` a pak zadejte "experimentální". Snadné spuštění bude najděte stránku po první písmena. Můžete se k němu výběrem také získat **nástroje | Možnosti** a rozšiřování **textového editoru**, pak **C/C++** a pak vyberete **experimentální**.

Tyto funkce jsou dostupné v instalaci Visual Studio 2017.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. V tématu [přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="enable-predictive-intellisense"></a>Povolení prediktivní IntelliSense

Prediktivní IntelliSense omezí počet výsledků, zobrazí se v rozevíracím seznamu IntelliSense tak, aby se zobrazily pouze výsledky, které jsou relevantní v kontextu. Pokud zadáte například <code>int x =</code> a vyvolání rozevíracího seznamu IntelliSense, zobrazí se jenom celá čísla nebo funkce, které vrací celá čísla. Prediktivní IntelliSense je ve výchozím nastavení vypnutý.

## <a name="enable-faster-project-load"></a>Povolit rychlejší načítání projektu

**Visual Studio 2017 verze 15.3 a novější**: Tato funkce je nyní nazývá **povolit ukládání do mezipaměti projektu** a přesunula [nastavení projektu VC ++](vcpp-project-settings-projects-and-solutions-options-dialog-box.md) stránku vlastností.
Tato možnost umožňuje sadě Visual Studio projektu ukládat data do mezipaměti, aby při příštím otevření projektu, je možné načíst data, nikoli znovu je computing z projektu souborů z mezipaměti. Pomocí data uložená v mezipaměti můžete výrazně urychlit čas načítání projektu.

## <a name="additional-features-in-the-visual-studio-marketplace"></a>Další funkce v sadě Visual Studio Marketplace

Můžete vyhledat další textový editor funkce [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=All&sortBy=Downloads). Příkladem je [C++ rychlé opravy](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.CQuickFixes2017), který podporuje následující:

- **Přidejte chybějící #include** -navrhuje relevantní #include na neznámé symbolů v kódu

- **Přidat pomocí oboru názvů nebo plnému určení symbol** – podobně jako předchozí položky, ale pro obory názvů

- **Přidejte chybějící středníkem**

- **Online nápovědy** -vyhledávání online nápovědy pro chybové zprávy

- a další...

## <a name="see-also"></a>Viz také:

- [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)
- [Refaktoring v jazyce C++ (VC Blog)](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
