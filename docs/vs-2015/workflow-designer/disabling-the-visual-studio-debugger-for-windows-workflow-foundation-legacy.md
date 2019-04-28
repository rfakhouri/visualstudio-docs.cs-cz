---
title: Zakázání ladicího programu pro programovací model Windows Workflow Foundation (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e5065de4ec0217123f76eb23d32bcb0facd25dcc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823338"
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
 [Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (starší verze)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md) [ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)