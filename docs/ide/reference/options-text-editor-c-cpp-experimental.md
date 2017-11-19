---
title: "Možnosti, textový Editor, C/C++ experimentální | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
ms.assetid: b9e9dda2-350c-460d-b368-37d6c5342eee
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: d67907a99851e09bf384c96b6ff6b87b4882cd30
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="options-text-editor-cc-experimental"></a>Možnosti, textový Editor, C/C++ experimentální
Změníte-li tyto možnosti, můžete změnit chování související s IntelliSense a procházení databáze, když jste programování v C nebo C++. Tyto funkce jsou skutečně experimentální a může být upravena nebo v budoucí verzi odebrána ze sady Visual Studio. Toto téma popisuje možnosti v nástroji Visual Studio 2017. Visual Studio 2015, najdete v části [možnosti, textový Editor, C/C++, experimentální](https://msdn.microsoft.com/library/mt591979.aspx) 
  
 Chcete-li získat přístup k této stránky vlastností, stiskněte **CTRL + Q** aktivovat `Quick Launch` a pak zadejte "experimentální". Snadné spuštění bude najděte stránku po první písmena. Můžete se k němu výběrem také získat **nástroje | Možnosti** a rozšiřování **textového editoru**, pak **C/C++**a pak vyberete **experimentální**.  

 Tyto funkce jsou dostupné v instalaci Visual Studio 2017.  
  
> [!NOTE]
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. V tématu [přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="enable-predictive-intellisense"></a>Povolení prediktivní Intellisense
Prediktivní IntelliSense omezí počet výsledků, zobrazí se v rozevíracím seznamu IntelliSense tak, aby se zobrazily pouze výsledky, které jsou relevantní v kontextu. Pokud zadáte například <code>int x =</code> a vyvolání rozevíracího seznamu IntelliSense, zobrazí se jenom celá čísla nebo funkce, které vrací celá čísla. Prediktivní IntelliSense je ve výchozím nastavení vypnutý.

## <a name="enable-faster-project-load"></a>Povolit rychlejší načítání projektu 
**Visual Studio 2017 verze 15.3 a novější**: Tato funkce je nyní nazývá **povolit ukládání do mezipaměti projektu** a přesunula [nastavení projektu VC ++](vcpp-project-settings-projects-and-solutions-options-dialog-box.md) stránku vlastností.
Tato možnost umožňuje sadě Visual Studio projektu ukládat data do mezipaměti, aby při příštím otevření projektu, je možné načíst data, nikoli znovu je computing z projektu souborů z mezipaměti. Pomocí data uložená v mezipaměti můžete výrazně urychlit čas načítání projektu.  

## <a name="additional-features-in-the-visual-studio-gallery"></a>Další funkce v Galerii Visual Studio
Další textový editor funkce v Galerii Visual Studia, najdete v seznamu [zde](http://go.microsoft.com/fwlink/?LinkId=692016). Příkladem je [C++ rychlé opravy](https://visualstudiogallery.msdn.microsoft.com/be91feef-8dc3-4f7a-ac9f-f34e7ca5918f), který podporuje následující:  
  
-   **Přidejte chybějící #include** -navrhuje relevantní #include na neznámé symbolů v kódu  
  
-   **Přidat pomocí oboru názvů nebo plnému určení symbol** – podobně jako předchozí položky, ale pro obory názvů  
  
-   **Přidejte chybějící středníkem**  
  
-   **Nápověda na webu MSDN** -MSDN vyhledávání pro chybové zprávy  
  
Můžete buď hover přes vlnovku na žárovky, nebo použijte výchozí klávesové zkratky Ctrl + tečka (Ctrl +.). Všimněte si, že pro klávesovou zkratku, vaše vsuvka nemusí být umístěný na konkrétní chyby nebo token; může být jednoduše na stejném řádku jako chyba k vyvolání návrhy pro všechno, co je na tomto řádku.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)   
 [Refaktoring v jazyce C++ (VC Blog)](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
