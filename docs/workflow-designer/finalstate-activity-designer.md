---
title: Návrhář aktivity FinalState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 6360be9522fd8a3640780407cb5252da41515536
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="finalstate-activity-designer"></a>Návrhář aktivity FinalState
<xref:System.Activities.Core.Presentation.FinalState> Designer se používá k vytvoření <xref:System.Activities.Statements.State> ukončující instance stav počítače.

## <a name="using-the-finalstate-activity-designer"></a>Pomocí návrháře FinalState aktivity
 **FinalState** designer se používá k vytvoření <xref:System.Activities.Statements.State> který je předem nakonfigurován jako ukončující stavu stav počítače. A <xref:System.Activities.Statements.State> vytvořený pomocí <xref:System.Activities.Core.Presentation.FinalState> Návrhář aktivity má jeho <xref:System.Activities.Statements.State.IsFinal%2A> vlastnost nastavena na hodnotu **true**, neobsahuje žádné <xref:System.Activities.Statements.State.Exit%2A> aktivity a žádné přechody pocházející z něj. Použít <xref:System.Activities.Core.Presentation.FinalState> Návrhář aktivity, které chcete přidat <xref:System.Activities.Statements.State> aktivity, který je předem nakonfigurovaný jako ukončující stavu stavový stroj, přetáhněte **FinalState** Návrhář aktivity z **stavový stroj**části **sada nástrojů** a umístěte jej do návrháře pracovních postupů. <xref:System.Activities.Core.Presentation.FinalState> Návrhář aktivity může být přetažen na <xref:System.Activities.Statements.StateMachine> a přechody přidat později; nebo přechod se dá vytvořit jako <xref:System.Activities.Core.Presentation.FinalState> Návrhář aktivity se ukončí. Další informace o vytváření přechody najdete v tématu [přechod](../workflow-designer/transition-activity-designer.md).

### <a name="state-activity-properties-in-the-workflow-designer"></a>Vlastnosti stavu aktivity v Návrháři pracovních postupů
 V následující tabulce jsou uvedeny vlastnosti, které se dá nastavit pomocí <xref:System.Activities.Core.Presentation.FinalState> designer a popisuje, jak se používají v návrháři. Některé z těchto vlastností můžete upravovat v tabulce vlastností a lze upravit některé na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.State> Návrhář aktivity v hlavičce. Výchozí hodnota je **stavu**. Hodnota se dá upravit v mřížku vlastností, nebo přímo v hlavičce Návrhář aktivity. <xref:System.Activities.Statements.State.DisplayName%2A> Se používá v cestě, která se zobrazí v horní části návrháře pracovních postupů.<br /><br /> I když <xref:System.Activities.Statements.State.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.State.Entry%2A>|False|Určuje akci, která nastane, když je tento stav se kvůli. Tato hodnota se dá nastavit tak, že přetáhnete aktivitu z **sada nástrojů** a vyřadit ho do <xref:System.Activities.Statements.State.Entry%2A> části stavu.|

## <a name="see-also"></a>Viz také

- [StateMachine](../workflow-designer/statemachine-activity-designer.md)
- [Stav](../workflow-designer/state-activity-designer.md)
- [Přechod](../workflow-designer/transition-activity-designer.md)