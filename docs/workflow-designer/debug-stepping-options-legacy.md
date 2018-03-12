---
title: "Ladění taktování možnosti (zastaralé) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- branch stepping
- stepping, options in workflow debugging
- debugging, stepping options
- debugging workflows, stepping options
- instance stepping
ms.assetid: 3e9e3041-68c7-4f16-9bd6-da5e5144744b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: beb4191b56bb0b2b0d80b30aa7956bc23d0cfa9d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="debug-stepping-options-legacy"></a>Ladění taktování možnosti (zastaralé)
Toto téma popisuje postup ladění [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace, které mají souběžných aktivity v Návrháři pracovních postupů starší verze systému Windows. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Když ladíte starší aktivity, které mají souběžné provádění, jako například **aktivity ParallelActivity** nebo **skupiny ConditionedActivityGroup**, můžete použít jednu z následujících dvou možností pro kroky prostřednictvím kódu .

-   **Větev krokování s.** Tento režim krokování umožňuje jednotlivé kroky a ladění konkrétní větve složené aktivity, například **aktivity ParallelActivity** nebo **ConditionalActivityGroup** aktivity. Pokud použijete tuto možnost k ladění, nebude Všimněte si, že dojde ke změně v ovládacím prvku z důvodu souběžných provádění jiných aktivit v pracovním postupu. Ladicí program pouze kroky prostřednictvím aktivity v aktuálně vybrané větve, zatímco ostatní aktivity v pracovním postupu mohou být prováděny současně. Například ve výchozím nastavení, levou krajní větve v **aktivity ParallelActivity** aktivity a první aktivitu podřízené **skupiny ConditionedActivityGroup** aktivity se používají pro krokování s. Uživatel je v případě zájmu ladění jiné pobočky nebo podřízené aktivity, explicitní zarážek musí být umístěny na větev nebo podřízené aktivity. Krokování s dál uvedené pobočky, když se aktivuje bod přerušení.

-   **Instance krokování s.** Tento režim krokování vám umožňuje procházet krok po kroku a ladění souběžně provádění aktivity v pracovním postupu. Pomocí této možnosti si všimnete, že dojde ke změně v ovládacím prvku při souběžně provádění aktivit spuštěných v rámci pracovního postupu.

 Standardně je vybraná možnost taktování větve a mohou uživatelé přepínat mezi dvě možnosti při ladění starší verze.

 Měli byste vybrat instanci krokování možnost při ladění pracovních starší verze stav počítače.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)
- [Postupy: Změna možností krokování při ladění (starší verze)](../workflow-designer/how-to-change-the-debug-stepping-option-legacy.md)