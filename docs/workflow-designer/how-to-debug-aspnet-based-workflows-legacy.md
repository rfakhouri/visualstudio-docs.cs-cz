---
title: "Postupy: ladění pracovních založený na technologii ASP.NET (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: aspnet
ms.openlocfilehash: 36905d8716b2f6a0fd961f668b7b5ca7c3ef623d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>Postupy: ladění pracovních založený na technologii ASP.NET (zastaralé)
Toto téma popisuje postup ladění [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]– na základě [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] v starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)].  
  
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
 [Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [Postupy: Nastavte zarážky v pracovních postupech (zastaralé)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)   
 [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)