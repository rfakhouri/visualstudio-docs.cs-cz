---
title: Možnosti, textový Editor, C/C++, experimentální
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
ms.openlocfilehash: dc0783ad10b01e8dcc7f5f85fa627ec142334597
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2018
ms.locfileid: "50218615"
---
# <a name="options-text-editor-cc-experimental"></a>Možnosti, textový Editor, C/C++, experimentální

Změnou tyto možnosti můžete změnit chování související se technologie IntelliSense a procházení databází, když programujete v jazyce C nebo C++. Tyto funkce jsou skutečně experimentální a může být změněna nebo v budoucí verzi odebrána ze sady Visual Studio. Toto téma popisuje možnosti v sadě Visual Studio 2017. Visual Studio 2015, najdete v části [možnosti, textový Editor, C/C++, experimentální](https://msdn.microsoft.com/library/mt591979.aspx)

Chcete-li získat přístup k této stránky vlastností, stiskněte **CTRL + Q** aktivovat `Quick Launch` a pak zadejte "experimentální". Snadné spuštění po prvních pár písmen najdete na stránce. Můžete také získáte k němu výběrem **nástroje | Možnosti** rozšiřuje **textový Editor**, pak **C/C++** a poté volbou **experimentální**.

Tyto funkce jsou dostupné v instalaci sady Visual Studio 2017.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Zobrazit [přizpůsobit prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="enable-predictive-intellisense"></a>Povolit prediktivní IntelliSense

Prediktivní IntelliSense omezí počet výsledků zobrazuje v rozevíracím seznamu technologie IntelliSense tak, aby se zobrazí pouze výsledky, které jsou relevantní v kontextu. Pokud zadáte například <code>int x =</code> a vyvolání rozevíracího seznamu technologie IntelliSense, zobrazí se jen celá čísla nebo funkce, které vrací celá čísla. Prediktivní IntelliSense je vypnuto ve výchozím nastavení.

## <a name="enable-faster-project-load"></a>Povolit rychlejší načítání projektů

**Visual Studio 2017 verze 15.3 nebo novější**: Tato funkce se teď nazývá **povolit ukládání projektů do mezipaměti** a byla přesunuta do [nastavení projektu VC ++](vcpp-project-settings-projects-and-solutions-options-dialog-box.md) stránku vlastností.
Tato možnost umožňuje sadě Visual Studio projekt ukládání dat do mezipaměti tak, aby při příštím otevření projektu, je možné načíst, uložit do mezipaměti dat spíše než znovu computingu ze souborů projektu. Pomocí dat uložených v mezipaměti může výrazně zkracují čas načtení projektu.

## <a name="additional-features-in-the-visual-studio-marketplace"></a>Další funkce v aplikaci Visual Studio Marketplace

Můžete procházet další textové funkce editoru [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=All&sortBy=Downloads). Příkladem je [C++ rychlých oprav](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.CQuickFixes2017), která podporuje následující:

- **Přidat chybějící #include** -navrhuje relevantní #include pro neznámý symboly ve vašem kódu

- **Přidat direktivu using obor názvů/plnému symbol** – podobně jako předchozí položce, ale pro obory názvů

- **Přidat chybějící středníkem**

- **Online Nápověda** -online nápovědě pro chybové zprávy

- a další...

## <a name="see-also"></a>Viz také:

- [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)
- [Refaktoring v jazyce C++ (VC blogu)](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
