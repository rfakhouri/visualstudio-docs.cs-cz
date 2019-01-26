---
title: Návrhář postupu provádění – Návrhář aktivity Sequence
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 82d7f8d61f3aa170d20bc46e1d7f530d56de0f25
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55001105"
---
# <a name="sequence-activity-designer"></a>Návrhář aktivity Sequence

<xref:System.Activities.Statements.Sequence> Aktivita obsahuje uspořádanou kolekci podřízené aktivity, které se provede v pořadí.

Dalším způsobem, jak provést sadu aktivit v pořadí se má používat <xref:System.Activities.Statements.Flowchart> aktivity. Zvažte použití [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) Pokud máte jednoduchou větvení nebo opakování ve smyčce toku programu, který chcete model diagramem.

## <a name="using-the-sequence-activity-designer"></a>Pomocí Návrhář aktivity Sequence

Chcete-li přidat <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte **pořadí** Návrhář aktivity z **nástrojů** a umístěte ho na povrch návrháře postupu provádění. Chcete-li přidat podřízené aktivity k tomuto <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte další aktivitu z **nástrojů** a umístěte ho na trojúhelník do pole text nápovědy "Sem přetáhněte aktivitu".

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Vlastnosti aktivity pořadí v Návrháři postupu provádění

Následující tabulka ukazuje <xref:System.Activities.Statements.Sequence> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností nebo na návrhové ploše.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Sequence> návrháře aktivit v záhlaví. Výchozí hodnota je sekvence. Hodnotu lze upravit v mřížce vlastností nebo přímo v hlavičce návrháře aktivit.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|

## <a name="see-also"></a>Viz také:

- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)