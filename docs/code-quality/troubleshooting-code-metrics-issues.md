---
title: Řešení potíží s metrikami kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e3d4e83d264e474a8ff578d1b832c4c2a2484bcd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54937071"
---
# <a name="troubleshooting-code-metrics-issues"></a>Řešení potíží s metrikami kódu
Některé z těchto problémů může dojít při shromažďování metrik kódu:

-   [Změny ve výpočtech složitost kódu sady Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Změny ve výpočtech složitost kódu sady Visual Studio 2010
 Pro stejnou funkci počítá metrika složitost kódu v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] může lišit od metrika počítá v předchozích verzích [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] v těchto situacích:

- Funkce obsahuje jeden nebo více bloky catch. V předchozích verzích [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], catch bloky nebyly zahrnutých do výpočtu. V [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], složitost každého bloku catch se přidá do složitost funkce.

- Funkce obsahuje příkaz switch (Select Case v jazyce Visual Basic). Kompilátor rozdíly mezi [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] a starší verze můžete vygenerovat různé kód jazyka MSIL pro některé příkazů přepínače, které obsahují propuštěním případy.

## <a name="see-also"></a>Viz také
 [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md)