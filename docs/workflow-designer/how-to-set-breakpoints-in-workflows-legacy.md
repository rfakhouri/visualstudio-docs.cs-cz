---
title: "Postupy: Nastavte zarážky v pracovních postupech (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- breakpoints, setting in workflows
- debugging, setting breakpoints in workflows
- debugging workflows, setting breakpoints
- workflows, setting breakpoints
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 89189feb32d84db8fb5c5eb7970faf325be1acd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-set-breakpoints-in-workflows-legacy"></a>Postupy: Nastavte zarážky v pracovních postupech (zastaralé)
Toto téma popisuje, jak nastavit zarážky [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] sestavení aplikace pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] při vaší [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] aplikace, musí cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Pokud používáte starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] k sestavení [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] aplikace, můžete nastavit zarážky v kódu jazyka C# a Visual Basic stejně jako v sadě Visual Studio. Podle očekávání, zastaví zpracování pracovního postupu u každé zarážky, který nastavíte.  
  
 Zarážku má tři stavy: *čekající*, *vázaný*, a *chyba*. Když nastavíte zarážku, čeká na vyřízení a je reprezentována dutý červenou ikonu. Když modul runtime načetl typ pracovního postupu, bude vázán a je reprezentován plnou červenou ikonou. Pokud zadáte nesprávný formát pro bod přerušení, jako s názvem aktivity, který není platný, zobrazí se okno s chyba. Zarážce přidána do okna zarážek, ale je označen s malým "x".  
  
 U aktivit na návrhovou plochu pracovního postupu můžete nastavit zarážky následujícími způsoby:  
  
-   Klikněte pravým tlačítkem na aktivitu a vyberte **zarážek \ vložit zarážku**.  
  
-   Vyberte aktivitu a stiskněte klávesu F9.  
  
-   Vyberte **nové zarážek** z **ladění** nabídky.  
  
     Tuto možnost můžete taky použít pro nastavení nového zarážky při ladění, při zastavení ladicího programu na zarážce.  
  
    > [!NOTE]
    >  Nastavení zarážek v pracovních postupech, vyvolá se nepodporuje.  
  
### <a name="to-set-a-breakpoint-using-the-new-breakpoint-option-on-the-debug-menu"></a>Chcete-li nastavit zarážky pomocí zarážek nové možnosti v nabídce ladění  
  
1.  Na **ladění** nabídce vyberte možnost **nové zarážek**.  
  
2.  Klikněte na tlačítko **rozdělit na funkce**.  
  
     **Nové zarážek** otevře se dialogové okno.  
  
3.  Zadejte název aktivity v **funkce** textového pole s použitím této syntaxe: `QualifiedActivityId[:[FullClassName][:InstanceId]]`.  
  
    > [!NOTE]
    >  Volitelně můžete místo použití název aktivity v **funkce** textového pole, můžete nastavit zarážky zadat absolutní cestu aktivity pracovního postupu. Předpokládejme například, máte řešení pracovního postupu s názvem **WorkflowConsoleApplication1** a pracovní postup v řešení s názvem **Workflow1** aktivitu názvem, který používá **Delay1**. Můžete použít název aktivity **Delay1** nebo zadejte cestu jako **Delay1:WorkflowConsoleApplication1.Workflow1** nebo **Delay1:WorkflowConsoleApplication1.Workflow1: { 6614886A-608E-412B-BF98-99FF1559DDDF}**.  
  
4.  Vyberte **pomocí IntelliSense** zaškrtnutím políčka ověřte název funkce.  
  
     Pokud není toto políčko zaškrtnuto, se provádí ověření názvu bez zarážek.  
  
5.  Vyberte **pracovního postupu** z **jazyk** seznamu.  
  
6.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění pracovních starší verze](../workflow-designer/debugging-legacy-workflows.md)   
 [Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)