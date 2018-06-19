---
title: 'Návrhář postupu provádění - postupy: Změna možnost ladění krokování (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31047cedd4e8772b9ebab4ef238a8fe32bc07663
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971980"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Postupy: Změna možnost ladění krokování (zastaralé)

Toto téma popisuje postup změny ladění krokování s možností pro aplikace Windows Workflow Foundation (WF) v Návrháři pracovních postupů starší verze systému Windows, které mají souběžných akce. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

Když ladíte starší aktivity, které mají souběžné provádění, jako například **aktivity ParallelActivity** nebo **skupiny ConditionedActivityGroup**, můžete použít jednu ze dvou možností k krokovat kód.

Použijte následující postup změna ladění krokování s možnost ve vašem projektu starší verze.

## <a name="procedures"></a>Procedury

### <a name="to-change-the-debug-stepping-option"></a>Chcete-li změnit možnosti taktování ladění

1.  Spuštění sady Visual Studio.

2.  Otevřít existující projekt starší verze nebo vytvořte nový projekt, který využívá souběžných aktivity a s cílem rozhraní .NET Framework verze 3.5 nebo WinFX.

3.  Na **pracovního postupu** nabídky ve starší verzi návrháře pracovních postupů, přejděte na **ladění**a pak přejděte na **krokování s možností**.

4.  Vyberte buď **Instance** nebo **větve**.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)
- [Možnosti krokování při ladění (starší verze)](../workflow-designer/debug-stepping-options-legacy.md)