---
title: Návrhář postupu provádění - krokování s možností pro ladění (zastaralé)
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- branch stepping
- stepping, options in workflow debugging
- debugging, stepping options
- debugging workflows, stepping options
- instance stepping
ms.assetid: 3e9e3041-68c7-4f16-9bd6-da5e5144744b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f46c0ab382a0e189c595e6e0f8aeb69c71814faf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969067"
---
# <a name="debug-stepping-options-legacy"></a>Ladění taktování možnosti (zastaralé)

Toto téma popisuje, jak ladit aplikace Windows Workflow Foundation (WF), které mají souběžných aktivity v Návrháři pracovních postupů starší verze systému Windows. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

Když ladíte starší aktivity, které mají souběžné provádění, jako například **aktivity ParallelActivity** nebo **skupiny ConditionedActivityGroup**, můžete použít jednu z následujících dvou možností pro kroky prostřednictvím kódu .

-   **Větev krokování s.** Tento režim krokování umožňuje jednotlivé kroky a ladění konkrétní větve složené aktivity, například **aktivity ParallelActivity** nebo **ConditionalActivityGroup** aktivity. Pokud použijete tuto možnost k ladění, nebude Všimněte si, že dojde ke změně v ovládacím prvku z důvodu souběžných provádění jiných aktivit v pracovním postupu. Ladicí program pouze kroky prostřednictvím aktivity v aktuálně vybrané větve, zatímco ostatní aktivity v pracovním postupu mohou být prováděny současně. Například ve výchozím nastavení, levou krajní větve v **aktivity ParallelActivity** aktivity a první aktivitu podřízené **skupiny ConditionedActivityGroup** aktivity se používají pro krokování s. Uživatel je v případě zájmu ladění jiné pobočky nebo podřízené aktivity, explicitní zarážek musí být umístěny na větev nebo podřízené aktivity. Krokování s dál uvedené pobočky, když se aktivuje bod přerušení.

-   **Instance krokování s.** Tento režim krokování vám umožňuje procházet krok po kroku a ladění souběžně provádění aktivity v pracovním postupu. Pomocí této možnosti si všimnete, že dojde ke změně v ovládacím prvku při souběžně provádění aktivit spuštěných v rámci pracovního postupu.

Standardně je vybraná možnost taktování větve a mohou uživatelé přepínat mezi dvě možnosti při ladění starší verze.

Měli byste vybrat instanci krokování možnost při ladění pracovních starší verze stav počítače.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)
- [Postupy: Změna možností krokování při ladění (starší verze)](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)