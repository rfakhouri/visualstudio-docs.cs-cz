---
title: 'Postupy: Změna možností krokování při ladění (starší verze) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 505f876b9c7943c8b039b74459552b77ce539477
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954450"
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Postupy: Změna možností krokování při ladění (starší verze)
Toto téma popisuje, jak změnit krokování možnosti ladění pro [!INCLUDE[wf](../includes/wf-md.md)] aplikací ve starší [!INCLUDE[wfd1](../includes/wfd1-md.md)] , které mají souběžných akce. Použijte starší [!INCLUDE[wfd2](../includes/wfd2-md.md)] potřeba cílit na platformu [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Když ladíte starší aktivity, které mají souběžné spouštění, jako například **aktivitě typu ParallelActivity** nebo **aktivitou skupiny ConditionedActivityGroup**, můžete použít jednu ze dvou možností pro jednotlivé kroky v kódu.  
  
 Použijte následující postup změna ladění krokování projektu starších verzí pracovních postupů.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-change-the-debug-stepping-option"></a>Chcete-li změnit možnosti krokování ladění  
  
1. Spusťte Visual Studio.  
  
2. Otevřete existující projekt starších verzí pracovních postupů nebo vytvořte nový projekt, který využívá souběžných aktivit a, který cílí na buď [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
3. Na **pracovního postupu** nabídky v starší [!INCLUDE[wfd2](../includes/wfd2-md.md)], přejděte na **ladění**a pak na **možnosti krokování**.  
  
4. Vyberte buď **Instance** nebo **větev**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)   
 [Možnosti krokování při ladění (starší verze)](../workflow-designer/debug-stepping-options-legacy.md)