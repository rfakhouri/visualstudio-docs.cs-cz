---
title: Návrhář postupu provádění – ladění pracovních starší verze
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 33a8358c5d62b938fc64d608c9b4546ab1745aaa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970374"
---
# <a name="debugging-legacy-workflows"></a>Ladění pracovních starší verze

Pokud používáte starší verzi návrháře pracovních postupů Windows v sadě Visual Studio k vytvoření aplikace Windows Workflow Foundation (WF), že target.NET Framework 3.0 nebo 3.5, můžete ladit vaše pracovní postupy jako libovolné jiné programy nastavení zarážek, připojení k procesům, a prozkoumání vláken a zásobníku volání. Máte také možnost ladění vzdáleně.

> [!NOTE]
> Pokud bylo nainstalovat a odinstalovat na váš počítač více verzí sady Visual Studio, WF3 ladění neúspěšně s jedním z existují následující dvě možnosti:
>
> -   Nejsou vaše zarážky.
> -   Zobrazí se následující zpráva:
>
> **Nelze spustit ladění na webovém serveru. Ladicí program není správně nainstalován.  Nelze ladění na požadovaný typ kódu.  Spusťte instalační program a nainstalujte nebo opravte ladicího programu.**
>
> Pokud některý z těchto scénářů dojde při ladění v rozhraní .NET Framework 3.0 nebo 3.5 pracovní postupy, provádění a opravit instalaci sady Visual Studio.

 Windows Workflow Foundation integruje se službou windows následující ladění standardní sady Visual Studio:

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