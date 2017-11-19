---
title: "Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 835ca509c86a9be27486ee257839c4e161221e4e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)
Toto téma popisuje, jak zakázat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicího programu pomocí konfiguračního souboru při sestavování [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Ve výchozím nastavení [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] ladicího programu pro [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] je povolený pro hostitelský proces. Zakázat ladění pracovního postupu, je nutné explicitně vypnout ho tak, že přidáte položku "DisableWorkflowDebugging"  **\<přepínače >** element v  **\<system.diagnostics >**oddíl konfiguračního souboru hostitele.  
  
 Následující příklad ukazuje, jak upravit hostitele konfigurační soubor zakázat ladění pracovního postupu.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="DisableWorkflowDebugging" value="true"/>  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Ladění pracovních starší verze](../workflow-designer/debugging-legacy-workflows.md)