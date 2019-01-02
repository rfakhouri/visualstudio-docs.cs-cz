---
title: Řešení potíží s Analýzou kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: troubleshooting
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c11ff3f6df9ba8ca2cd58f89fd3eec89e6a9abb2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53876043"
---
# <a name="troubleshooting-code-analysis-issues"></a>Řešení potíží s Analýzou kódu
Toto téma obsahuje informace o odstraňování potíží pro následující problémy s analýzou kódu sady Visual Studio.

-   [Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio](#ChildRuleSetChangesInPreviousVersions)

##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Změny v Visual Studio 2010 pravidlo Set nejsou v předchozích verzích sady Visual Studio
 Když vytvoříte pravidlo nastavit [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] , která obsahuje podřízenou sadu pravidel, nejde použít ke změně podřízené sady pravidel v nastavují spuštění analýzu kódu na počítačích, které používají starší verzi sady Visual Studio. Pokud chcete tento problém vyřešit, musíte Vynutit přepsání sady pravidel nadřazený, který je sada pravidel, která obsahuje podřízené sady pravidel.

1. Otevřít nadřazený pravidlo nastavené [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

2. Proveďte změnu, jako je například přidávání nebo odebírání pravidlo a potom uložte sady pravidel.

3. Znovu otevřít sadu pravidel, zrušení změny a potom uložte pravidlo znovu nastavit.

## <a name="see-also"></a>Viz také

- [Analýza kvality aplikace](../code-quality/code-analysis-for-managed-code-overview.md)
- [Analýza kvality spravovaného kódu](../code-quality/code-analysis-for-managed-code-overview.md)
- [Použití sad pravidel k seskupování pravidel analýzy kódu](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)