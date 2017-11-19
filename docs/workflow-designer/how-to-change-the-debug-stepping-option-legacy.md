---
title: "Postupy: Změna možnost ladění krokování (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- branch stepping
- debugging, stepping options
- debugging workflows, stepping options
- stepping, changing options
- instance stepping
ms.assetid: aedc06af-d58a-44d6-aee4-f397f1f923a0
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: ff11186c82102230ec939c0c9b1c5aba69df7f3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-change-the-debug-stepping-option-legacy"></a>Postupy: Změna možnost ladění krokování (zastaralé)
Toto téma popisuje, jak změnit možnosti taktování ladění pro [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] mají souběžných akce. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Když ladíte starší aktivity, které mají souběžné provádění, jako například **aktivity ParallelActivity** nebo **skupiny ConditionedActivityGroup**, můžete použít jednu ze dvou možností k krokovat kód.  
  
 Použijte následující postup změna ladění krokování s možnost ve vašem projektu starší verze.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-change-the-debug-stepping-option"></a>Chcete-li změnit možnosti taktování ladění  
  
1.  Spuštění sady Visual Studio.  
  
2.  Otevřít existující projekt starší verze nebo vytvořte nový projekt, který používá souběžných aktivity a která se zaměřuje buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
3.  Na **pracovního postupu** nabídky v starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], přejděte na **ladění**a pak přejděte na **krokování s možností**.  
  
4.  Vyberte buď **Instance** nebo **větve**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění pracovních starší verze](../workflow-designer/debugging-legacy-workflows.md)   
 [Ladění taktování možnosti (zastaralé)](../workflow-designer/debug-stepping-options-legacy.md)