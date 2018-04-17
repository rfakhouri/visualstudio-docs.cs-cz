---
title: 'Postupy: ladění kódu XAML pomocí návrháře pracovních postupů | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: c0ac923de3c5381add6f0a33612258e8b9d64824
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Postupy: ladění kódu XAML pomocí návrháře pracovních postupů
Pracovní postupy jsou definována v XAML. Reprezentace uživatelského rozhraní pracovního postupu je postavená na stromu XAML definice pracovního postupu. Ladění prostředí je podobná ladění pracovních postupů v Návrháři pracovních postupů Windows. Například při ladění XAML, místní, sledovat a vláken windows fungovat stejným způsobem jako ve [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ladění. Kromě toho je zobrazení zásobníku volání při ladění jazyka XAML na základě řádku hierarchické zobrazení toku spuštění pracovního postupu.

> [!NOTE]
> Pokud XAML pro pracovní postup nachází ve stejném sestavení jako aktivity, část sestavení pro názvy tříd, které nejsou zahrnuty. Bez této část názvy tříd (aktivita) nelze načíst XAML za běhu. Není doporučeno definovat aktivity v o stejný obor názvů, jako je hlavní projekt; v opačném XAML bude nutné ručně upravovat po upravovaný v návrháři.

### <a name="to-debug-workflow-xaml"></a>Chcete-li ladit pracovního postupu XAML

1.  Otevřete projekt pracovního postupu nebo aktivity v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

2.  Nastavit zarážky aktivity nebo aktivity, kterou chcete ladit, jak je popsáno v [postupy: nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md).

3.  Klikněte pravým tlačítkem na soubor XAML, který obsahuje definice pracovního postupu a vyberte **kód zobrazení**. Zobrazí se zarážku zobrazí na stejném řádku jako deklarace element XAML aktivity, která nastavíte zarážkou na v zobrazení návrhu.

4.  Vyvolání ladicího programu, jak je popsáno v [postupy: volání ladicí program pracovního postupu](../workflow-designer/how-to-invoke-the-workflow-debugger.md).

5.  Při provádění kódu dosáhne mezi body přerušení, bude mít zvýrazněná element jazyka XAML přidružené k této zarážek. Chcete-li přesunout na další zarážku, použijte **F10** nebo **F11** klíč.

## <a name="see-also"></a>Viz také

- [Postupy: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Postupy: Spuštění ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md)