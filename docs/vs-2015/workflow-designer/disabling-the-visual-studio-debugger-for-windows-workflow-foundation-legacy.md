---
title: Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (starší verze) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 9fd51e47ff92e231507e56bb3eacad212a47c90d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669841"
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Zakázání ladicího programu sady Visual Studio pro programovací model Windows Workflow Foundation (starší verze)
Toto téma popisuje, jak zakázat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladicího programu při sestavování je používán konfigurační soubor [!INCLUDE[wf](../includes/wf-md.md)] aplikací ve starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Použijte starší [!INCLUDE[wfd2](../includes/wfd2-md.md)] potřeba cílit na platformu [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Ve výchozím nastavení [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] ladicího programu pro [!INCLUDE[wf](../includes/wf-md.md)] je povolený pro hostitelský proces. Pokud chcete zakázat ladění pracovního postupu, je nutné explicitně vypnout ho tak, že přidáte položku "DisableWorkflowDebugging"  **\<přepínače >** prvek  **\<system.diagnostics >** souboru konfigurace hostitele.  
  
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
 [Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (starší verze)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)