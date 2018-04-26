---
title: Návrhář postupu provádění – Pokud návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 58adde57c6de49a4abb0456ba5c80df27a45b069
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="if-activity-designer"></a>Pokud návrhář aktivity

<xref:System.Activities.Statements.If> Aktivita vyhodnotí podmínku a provede aktivitu v závislosti na výsledky tohoto vyhodnocení. Tato aktivita je velmi užitečné při použití procedurální modelování styl programování. <xref:System.Activities.Statements.If> Aktivity může být vnořena ve <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Parallel> aktivity, například. Pokud používáte <xref:System.Activities.Statements.Flowchart> aktivity, zvažte použití <xref:System.Activities.Statements.FlowDecision> aktivity místo.

## <a name="if-properties-in-the-workflow-designer"></a>Pokud vlastnosti v Návrháři pracovních postupů

V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.If> vlastnosti aktivity a popisuje, jak je používat v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.If.Condition%2A>|Hodnota TRUE|Podmínku, která určuje, která podřízené aktivita se má spustit. Chcete-li nastavit <xref:System.Activities.Statements.If.Condition%2A>, zadejte výraz jazyka Visual Basic v **podmínku** pole na **Pokud** aktivity návrháře nebo v tabulce vlastností.|
|<xref:System.Activities.Statements.If.Else%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **false**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Else%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **Else** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|
|<xref:System.Activities.Statements.If.Then%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **true**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Then%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **pak** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|

## <a name="see-also"></a>Viz také

- [Pořadí](../workflow-designer/sequence-activity-designer.md)
- [Paralelní](../workflow-designer/parallel-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)