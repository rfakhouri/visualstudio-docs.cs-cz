---
title: Řešení potíží s metrikami kódu
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b8c5dfd9c388e8c2ab4ce83ca0c952851616835c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="troubleshooting-code-metrics-issues"></a>Řešení potíží s metrikami kódu
Můžete shromažďovat metriky kódu setkat s některé z následujících důvodů:

-   [Změny ve výpočtech složitost kódu Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Změny ve výpočtech složitost kódu Visual Studio 2010
 Pro stejnou funkci Vypočítat metrika složitost kódu v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] může lišit od metrika vypočítána dřívějších verzích [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] pro následující případy:

-   Funkce obsahuje jeden nebo více catch – bloky. V předchozích verzích [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], catch – bloky nebyly zahrnutých do výpočtu. V [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], složitost každý blok catch se přidá do složitosti funkce.

-   Funkce obsahuje příkaz switch (Select Case v jazyce Visual Basic). Kompilátoru rozdíly mezi [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] a dřívějších verzí může generovat různý kód MSIL pro některé příkazů přepínače, které obsahují patří prostřednictvím případů.

## <a name="see-also"></a>Viz také
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)