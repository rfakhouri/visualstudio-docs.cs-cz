---
title: Potíží s metrikami kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0fb95a46c74c502a14034d621b67895f495256d0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54753172"
---
# <a name="troubleshooting-code-metrics-issues"></a>Řešení potíží s metrikami kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Některé z těchto problémů může dojít při shromažďování metrik kódu:  
  
-   [Změny ve výpočtech složitost kódu sady Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Změny ve výpočtech složitost kódu sady Visual Studio 2010  
 Pro stejnou funkci počítá metrika složitost kódu v [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] může lišit od metrika počítá v předchozích verzích [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] v těchto situacích:  
  
-   Funkce obsahuje jeden nebo více bloky catch. V předchozích verzích [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)], catch bloky nebyly zahrnutých do výpočtu. V [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)], složitost každého bloku catch se přidá do složitost funkce.  
  
-   Funkce obsahuje příkaz switch (Select Case v jazyce Visual Basic). Kompilátor rozdíly mezi [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] a starší verze můžete vygenerovat různé kód jazyka MSIL pro některé příkazů přepínače, které obsahují propuštěním případy.  
  
## <a name="see-also"></a>Viz také  
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
