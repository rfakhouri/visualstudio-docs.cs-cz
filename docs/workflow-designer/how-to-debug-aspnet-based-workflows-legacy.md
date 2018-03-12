---
title: "Postupy: ladění pracovních založený na technologii ASP.NET (zastaralé) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- aspnet
ms.openlocfilehash: 3c62d4df23eb494d52a387da5e1727e4419f2ce8
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Postupy: ladění pracovních založený na technologii ASP.NET (zastaralé)
Toto téma popisuje postup ladění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]– na základě [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] v Návrháři pracovních postupů starší verze systému Windows.

 Můžete ladit starší verze pracovní postupy, které jsou spuštěny v technologii ASP.NET nebo starší verze pracovní postupy, které jsou publikovány jako webovou službu se připojuje k procesu, ve kterém je hostovaná pracovního postupu.

### <a name="to-debug-an-aspnet-based-workflow"></a>Chcete-li ladit pracovním postupu založený na technologii ASP.NET

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