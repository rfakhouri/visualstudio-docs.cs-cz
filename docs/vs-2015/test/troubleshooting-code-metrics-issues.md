---
title: Řešení potíží s metrikami kódu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5a02dbc4840729d5004b0815175f626fc8760711
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416976"
---
# <a name="troubleshooting-code-metrics-issues"></a>Řešení potíží s metrikami kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když shromáždíte metriky kódu, může dojít k některým z následujících problémů:

- [Změny ve výpočtech složitosti kódu sady Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

## <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>Změny ve výpočtech složitosti kódu sady Visual Studio 2010

Pro stejnou funkci se metrika složitosti kódu vypočtená [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] v může lišit od metriky počítané předchozími [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] verzemi nástroje v následujících situacích:

- Funkce obsahuje jeden nebo více bloků catch. V předchozích verzích systému [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]nebyly bloky catch zahrnuty do výpočtu. V [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]systému je složitost každého bloku catch přidána ke složitosti funkce.

- Funkce obsahuje příkaz switch (Select Case in VB). Rozdíly ve kompilátorech mezi [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] a staršími verzemi mohou vygenerovat jiný kód jazyka MSIL pro některé příkazy Switch, které obsahují případy vzpadne.

## <a name="see-also"></a>Viz také:

- [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
