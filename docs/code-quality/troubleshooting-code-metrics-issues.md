---
title: Potíží s metrikami kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d8d49271d394d581349f97478a81af04b6766f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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