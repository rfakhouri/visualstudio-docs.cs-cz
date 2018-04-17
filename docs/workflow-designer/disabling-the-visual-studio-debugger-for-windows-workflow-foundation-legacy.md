---
title: Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a609062f3f84538f7c1655cd5ca82971fc608f62
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)

Toto téma popisuje, jak zakázat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicího programu pomocí konfiguračního souboru při sestavování [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace v Návrháři pracovních postupů starší verze systému Windows. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Ve výchozím nastavení [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] ladicího programu pro [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] je povolený pro hostitelský proces. Zakázat ladění pracovního postupu, je nutné explicitně vypnout ho tak, že přidáte položku "DisableWorkflowDebugging"  **\<přepínače >** element v  **\<system.diagnostics >**oddíl konfiguračního souboru hostitele.

 Následující příklad ukazuje, jak upravit hostitele konfigurační soubor zakázat ladění pracovního postupu.

```xml
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

- [Spuštění ladicího programu sady Visual Studio pro programovací model Windows Workflow Foundation (starší verze)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)