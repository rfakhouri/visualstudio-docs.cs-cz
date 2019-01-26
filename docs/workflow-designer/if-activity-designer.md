---
title: Návrhář postupu provádění – Pokud návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f069da9bb84074544cc388ab2bf7fa1eab3c7595
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54917156"
---
# <a name="if-activity-designer"></a>Návrhář aktivity If

<xref:System.Activities.Statements.If> Aktivity vyhodnocuje podmínku a provede aktivitu v závislosti na výsledcích hodnocení. Tato aktivita je nejužitečnější při použití procedurální modelování styl programování. <xref:System.Activities.Statements.If> Aktivity mohou být vnořené uvnitř <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Parallel> aktivity, například. Pokud používáte <xref:System.Activities.Statements.Flowchart> aktivity, zvažte použití <xref:System.Activities.Statements.FlowDecision> aktivity místo.

## <a name="if-properties-in-the-workflow-designer"></a>Pokud vlastnosti v Návrháři postupu provádění

V následující tabulce jsou uvedeny nejužitečnější <xref:System.Activities.Statements.If> vlastnosti aktivit a popisuje, jak je používat v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Statements.If.Condition%2A>|Pravda|Podmínka, která určuje, které podřízené aktivity ke spuštění. Chcete-li nastavit <xref:System.Activities.Statements.If.Condition%2A>, zadejte výraz jazyka Visual Basic v **podmínku** pole na **Pokud** aktivity návrháře nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.If.Else%2A>|False|Aktivita spustit, když <xref:System.Activities.Statements.If.Condition%2A> je **false**. Přidat aktivitu, která provádí <xref:System.Activities.Statements.If.Else%2A> větev, přetáhněte aktivitu z **nástrojů** do **Else** pole na **Pokud** Návrhář aktivity s text nápovědy " Sem přetáhněte aktivitu".|
|<xref:System.Activities.Statements.If.Then%2A>|False|Aktivita spustit, když <xref:System.Activities.Statements.If.Condition%2A> je **true**. Přidat aktivitu, která provádí <xref:System.Activities.Statements.If.Then%2A> větev, přetáhněte aktivitu z **nástrojů** do **pak** pole na **Pokud** Návrhář aktivity s text nápovědy " Sem přetáhněte aktivitu".|

## <a name="see-also"></a>Viz také:

- [Sequence](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)