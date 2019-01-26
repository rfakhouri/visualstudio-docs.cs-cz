---
title: Návrhář postupu provádění – Návrhář aktivity StateMachine
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 52cbd0e27934d5d13c0e83c6c8e3e87281aa1b5a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972898"
---
# <a name="statemachine-activity-designer"></a>Návrhář aktivity StateMachine

<xref:System.Activities.Statements.StateMachine> Aktivity obsahuje kolekci stavů modelů a pracovní postupy pomocí paradigma známé stav počítače.

## <a name="using-the-statemachine-activity-designer"></a>Pomocí Návrhář aktivity StateMachine

Přidat <xref:System.Activities.Statements.StateMachine> aktivity, přetáhněte **stavový stroj StateMachine** Návrhář aktivity z **stavového stroje** část **nástrojů** a umístěte ho do návrháře postupu provádění povrchu. Přidáte stav podřízené tomuto <xref:System.Activities.Statements.StateMachine> aktivity, přetáhněte <xref:System.Activities.Statements.State> nebo <xref:System.Activities.Core.Presentation.FinalState> z **nástrojů** a umístěte ho do **stavový stroj StateMachine**.

### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>Vlastnosti aktivity StateMachine v Návrháři postupu provádění

Následující tabulka ukazuje <xref:System.Activities.Statements.StateMachine> vlastnosti, které lze nastavit pomocí návrháře pracovních postupů a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé lze upravit na návrhové ploše.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.StateMachine> návrháře aktivit v záhlaví. Výchozí hodnota je **stavový stroj StateMachine**. Hodnotu lze upravit v mřížce vlastností nebo přímo v hlavičce návrháře aktivit. <xref:System.Activities.Activity.DisplayName%2A> Se používá v navigace s popisem cesty, který se zobrazí v horní části návrháře postupu provádění.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|

## <a name="see-also"></a>Viz také:

- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)