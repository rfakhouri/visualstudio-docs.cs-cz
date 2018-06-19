---
title: Návrhář postupu provádění - zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 473ee507e35f5ec5df902df64ee34326dcf90a2b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969962"
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Zakázání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)

Toto téma popisuje, jak zakázat pomocí konfiguračního souboru, při vytváření aplikace Windows Workflow Foundation (WF) v Návrháři pracovních postupů starší verze Windows ladicí program Visual Studio. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

 Ve výchozím nastavení je Visual Studio ladicí program pro Windows Workflow Foundation (WF) povoleno pro hostitelský proces. Zakázat ladění pracovního postupu, je nutné explicitně vypnout ho tak, že přidáte položku "DisableWorkflowDebugging"  **\<přepínače >** element v  **\<system.diagnostics >** oddíl konfiguračního souboru hostitele.

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