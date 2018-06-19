---
title: 'Návrhář postupu provádění - postupy: Nastavte zarážky v pracovních postupech (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- breakpoints, setting in workflows
- debugging, setting breakpoints in workflows
- debugging workflows, setting breakpoints
- workflows, setting breakpoints
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0c70b630404830fa8c733a7310e4700da8f08b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975192"
---
# <a name="how-to-set-breakpoints-in-workflows-legacy"></a>Postupy: Nastavte zarážky v pracovních postupech (zastaralé)

Toto téma popisuje, jak nastavit zarážky ve Windows Workflow Foundation (WF) sestavení aplikace pomocí návrháře pracovních postupů starší verze systému Windows. Pokud aplikace Windows Workflow Foundation musí cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

 Pokud používáte starší verzi návrháře pracovních postupů v sadě Visual Studio 2010 sestavit aplikaci pro Windows Workflow Foundation, můžete nastavit zarážky v C# a kód jazyka Visual Basic stejně jako v sadě Visual Studio. Podle očekávání, zastaví zpracování pracovního postupu u každé zarážky, který nastavíte.

 Zarážku má tři stavy: *čekající*, *vázaný*, a *chyba*. Když nastavíte zarážku, čeká na vyřízení a je reprezentována dutý červenou ikonu. Když modul runtime načetl typ pracovního postupu, bude vázán a je reprezentován plnou červenou ikonou. Pokud zadáte nesprávný formát pro bod přerušení, jako s názvem aktivity, který není platný, zobrazí se okno s chyba. Zarážce přidána do okna zarážek, ale je označen s malým "x".

 U aktivit na návrhovou plochu pracovního postupu můžete nastavit zarážky následujícími způsoby:

-   Klikněte pravým tlačítkem na aktivitu a vyberte **zarážek \ vložit zarážku**.

-   Vyberte aktivitu a stiskněte klávesu F9.

-   Vyberte **nové zarážek** z **ladění** nabídky.

     Tuto možnost můžete taky použít pro nastavení nového zarážky při ladění, při zastavení ladicího programu na zarážce.

    > [!NOTE]
    > Nastavení zarážek v pracovních postupech, vyvolá se nepodporuje.

### <a name="to-set-a-breakpoint-using-the-new-breakpoint-option-on-the-debug-menu"></a>Chcete-li nastavit zarážky pomocí zarážek nové možnosti v nabídce ladění

1.  Na **ladění** nabídce vyberte možnost **nové zarážek**.

2.  Klikněte na tlačítko **rozdělit na funkce**.

     **Nové zarážek** otevře se dialogové okno.

3.  Zadejte název aktivity v **funkce** textového pole s použitím této syntaxe: `QualifiedActivityId[:[FullClassName][:InstanceId]]`.

    > [!NOTE]
    > Volitelně můžete místo použití název aktivity v **funkce** textového pole, můžete nastavit zarážky zadat absolutní cestu aktivity pracovního postupu. Předpokládejme například, máte řešení pracovního postupu s názvem **WorkflowConsoleApplication1** a pracovní postup v řešení s názvem **Workflow1** aktivitu názvem, který používá **Delay1**. Můžete použít název aktivity **Delay1** nebo zadejte cestu jako **Delay1:WorkflowConsoleApplication1.Workflow1** nebo **Delay1:WorkflowConsoleApplication1.Workflow1: { 6614886A-608E-412B-BF98-99FF1559DDDF}**.

4.  Vyberte **pomocí IntelliSense** zaškrtnutím políčka ověřte název funkce.

     Pokud není toto políčko zaškrtnuto, se provádí ověření názvu bez zarážek.

5.  Vyberte **pracovního postupu** z **jazyk** seznamu.

6.  Click **OK**.

## <a name="see-also"></a>Viz také

- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)
- [Spuštění ladicího programu sady Visual Studio pro programovací model Windows Workflow Foundation (starší verze)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)