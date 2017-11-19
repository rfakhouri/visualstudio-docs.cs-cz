---
title: "Postupy: ladění kódu XAML pomocí návrháře pracovních postupů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: c73e053cc3e3dc53101595f00dcd8fd45da8abd7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Postupy: ladění kódu XAML pomocí návrháře pracovních postupů
Pracovní postupy jsou definována v XAML. Reprezentace uživatelského rozhraní pracovního postupu je postavená na stromu XAML definice pracovního postupu. Je podobná ladění pracovních postupů v prostředí ladění [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Například při ladění XAML, místní, sledovat a vláken windows fungovat stejným způsobem jako ve [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ladění. Kromě toho je zobrazení zásobníku volání při ladění jazyka XAML na základě řádku hierarchické zobrazení toku spuštění pracovního postupu.  
  
> [!NOTE]
>  Pokud XAML pro pracovní postup nachází ve stejném sestavení jako aktivity, část sestavení pro názvy tříd, které nejsou zahrnuty. Bez této část názvy tříd (aktivita) nelze načíst XAML za běhu. Není doporučeno definovat aktivity v o stejný obor názvů, jako je hlavní projekt; v opačném XAML bude nutné ručně upravovat po upravovaný v návrháři.  
  
### <a name="to-debug-workflow-xaml"></a>Chcete-li ladit pracovního postupu XAML  
  
1.  Otevřete projekt pracovního postupu nebo aktivity v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
2.  Nastavit zarážky aktivity nebo aktivity, kterou chcete ladit, jak je popsáno v [postupy: nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md).  
  
3.  Klikněte pravým tlačítkem na soubor XAML, který obsahuje definice pracovního postupu a vyberte **kód zobrazení**. Zobrazí se zarážku zobrazí na stejném řádku jako deklarace element XAML aktivity, která nastavíte zarážkou na v zobrazení návrhu.  
  
4.  Vyvolání ladicího programu, jak je popsáno v [postupy: volání ladicí program pracovního postupu](../workflow-designer/how-to-invoke-the-workflow-debugger.md).  
  
5.  Při provádění kódu dosáhne mezi body přerušení, bude mít zvýrazněná element jazyka XAML přidružené k této zarážek. Chcete-li přesunout na další zarážku, použijte **F10** nebo **F11** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavte zarážky v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [Postupy: volání ladicí program pracovního postupu](../workflow-designer/how-to-invoke-the-workflow-debugger.md)