---
title: "Návrhář aktivity StateMachine | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 41215bea8c437d35d62448617eb5575b07bbca6a
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="statemachine-activity-designer"></a>Návrhář aktivity StateMachine
<xref:System.Activities.Statements.StateMachine> Aktivity obsahuje kolekci stavů a modely workflowů pomocí zlepší známé stav počítače.

## <a name="using-the-statemachine-activity-designer"></a>Pomocí návrháře StateMachine aktivity
 Přidat <xref:System.Activities.Statements.StateMachine> aktivity, přetáhněte **StateMachine** Návrhář aktivity z **stavu počítače** části **sada nástrojů** a umístěte jej do pracovního postupu systému Windows Plochu návrháře. Chcete-li přidat stav podřízených k tomuto <xref:System.Activities.Statements.StateMachine> aktivity, přetáhněte <xref:System.Activities.Statements.State> nebo <xref:System.Activities.Core.Presentation.FinalState> z **sada nástrojů** a umístěte jej do **StateMachine**.

### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>Vlastnosti StateMachine aktivity v Návrháři pracovních postupů
 Následující tabulce je zobrazena <xref:System.Activities.Statements.StateMachine> vlastnosti, které se dá nastavit pomocí návrháře pracovních postupů a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v tabulce vlastností a některé můžete upravit na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.StateMachine> Návrhář aktivity v hlavičce. Výchozí hodnota je **StateMachine**. Hodnota se dá upravit v mřížku vlastností, nebo přímo v hlavičce Návrhář aktivity. <xref:System.Activities.Activity.DisplayName%2A> Se používá v cestě, která se zobrazí v horní části návrháře pracovních postupů.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|

## <a name="see-also"></a>Viz také

- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)