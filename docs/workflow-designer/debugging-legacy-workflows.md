---
title: Ladění pracovních starší | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2710266446e285d9107f4450c09ffe2e8e87e090
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-legacy-workflows"></a>Ladění pracovních starší verze

Pokud používáte starší verzi návrháře pracovních postupů Windows v [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] k sestavení [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace target.NET Framework 3.0 nebo 3.5, můžete nastavení zarážek, připojení k procesům a zkoumání ladění vaše pracovní postupy jako jakýkoli jiný program vláken a zásobníku volání. Máte také možnost ladění vzdáleně.

> [!NOTE]
> Pokud bylo nainstalovat a odinstalovat na váš počítač více verzí sady Visual Studio, WF3 ladění neúspěšně s jedním z existují následující dvě možnosti:
>
> -   Nejsou vaše zarážky.
> -   Zobrazí se následující zpráva:
>
> **Nelze spustit ladění na webovém serveru. Ladicí program není správně nainstalován.  Nelze ladění na požadovaný typ kódu.  Spusťte instalační program a nainstalujte nebo opravte ladicího programu.**
>
> Pokud některý z těchto scénářů dojde při ladění v rozhraní .NET Framework 3.0 nebo 3.5 pracovní postupy, provádění a opravit instalaci sady Visual Studio.

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] se integruje s následující standard [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladění windows:

-   **Breakpoint –**: funguje podle očekávání, můžete však zadat aktivitu pro název funkce.

-   **Zásobník volání**: změněné zajistit přehled aktivit, které mají spustit v instanci pracovního postupu. Položky v **zásobníkem volání** okna jsou nejprve v úrovni hledání provádění aktivity. Dvakrát klikněte na položku pro přesunout zaměření na vybranou aktivitou.

-   **Vlákna**: poskytuje ID instance k instanci pracovního postupu, který je právě laděn.

 Visual Studio pro Windows Workflow Foundation nepodporuje následující funkce ladění:

-   Podmíněné zarážky na plochu návrháře.

-   QuickWatch.

-   Nastavit další příkaz.

-   Spusťte ke kurzoru.

-   Upravit a pokračovat.

-   Ladění za běhu.

-   Ladění ve smíšeném režimu.