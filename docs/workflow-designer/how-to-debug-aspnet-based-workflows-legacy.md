---
title: 'Návrhář postupu provádění - postupy: ladění pracovních založený na technologii ASP.NET (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 7bf16a6a88c5d4cd063f1c32ca846031d8b2588d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Postupy: ladění pracovních založený na technologii ASP.NET (zastaralé)

Toto téma popisuje, jak ladit aplikace založený na technologii ASP.NET Windows Workflow Foundation (WF), že cíl buď rozhraní .NET Framework verze 3.5 nebo WinFX v Návrháři pracovních postupů starší verze systému Windows.

Můžete ladit starší verze pracovní postupy, které jsou spuštěny v technologii ASP.NET nebo starší verze pracovní postupy, které jsou publikovány jako webovou službu se připojuje k procesu, ve kterém je hostovaná pracovního postupu.

## <a name="to-debug-an-aspnet-based-workflow"></a>Chcete-li ladit pracovním postupu založený na technologii ASP.NET

1.  Povolení ladění pro aplikace ASP.NET nastavením **debug = true** v souboru web.config.

2.  Nastavit jako spouštěný projekt knihovně pracovního postupu a nastavit zarážky pro pracovní postup.

3.  Zadejte adresu URL výchozí webové stránky ve vlastnostech projektu pracovního postupu **ladění** možnost **spuštění prohlížeče s externí adresu URL** textové pole.

4.  Vyberte **připojit k procesu** na **ladění** nabídky.

5.  Vyberte proces pro připojení z **dostupné procesy** seznamu.

     Připojte k procesu w3wp.exe, webdev.webserver nebo aspnet_wp, ve kterém je hostovaná pracovního postupu.

6.  Klikněte na tlačítko **vyberte** vedle **připojit k** textového pole.

     **Vybrat typ kódu** zobrazí se dialogové okno.

7.  Vyberte **ladění tyto typy kódu** a vyberte **pracovního postupu**.

8.  Click **OK**.

9. Klikněte na tlačítko **připojit**.

10. Výchozí webové stránky, otevřete v prohlížeči a spusťte pracovní postup.

## <a name="see-also"></a>Viz také

- [Spuštění ladicího programu sady Visual Studio pro programovací model Windows Workflow Foundation (starší verze)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [Postupy: Nastavení zarážek v pracovních postupech (starší verze)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)