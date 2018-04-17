---
title: 'Postupy: Změna možnost ladění krokování (zastaralé) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: aedb8e738dc2e6ca2b066dd9a2cd42e332bbd8be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Postupy: Změna možnost ladění krokování (zastaralé)
Toto téma popisuje, jak změnit možnosti taktování ladění pro [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v Návrháři pracovních postupů starší verze systému Windows, které mají souběžných akce. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Když ladíte starší aktivity, které mají souběžné provádění, jako například **aktivity ParallelActivity** nebo **skupiny ConditionedActivityGroup**, můžete použít jednu ze dvou možností k krokovat kód.

 Použijte následující postup změna ladění krokování s možnost ve vašem projektu starší verze.

## <a name="procedures"></a>Procedury

#### <a name="to-change-the-debug-stepping-option"></a>Chcete-li změnit možnosti taktování ladění

1.  Spuštění sady Visual Studio.

2.  Otevřít existující projekt starší verze nebo vytvořte nový projekt, který používá souběžných aktivity a která se zaměřuje buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

3.  Na **pracovního postupu** nabídky v starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], přejděte na **ladění**a pak přejděte na **krokování s možností**.

4.  Vyberte buď **Instance** nebo **větve**.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)
- [Možnosti krokování při ladění (starší verze)](../workflow-designer/debug-stepping-options-legacy.md)