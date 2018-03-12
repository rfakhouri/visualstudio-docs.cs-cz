---
title: "Pokud návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 38315b493bd1349efcea5c511378d38eb05ca97d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="if-activity-designer"></a>Pokud návrhář aktivity
<xref:System.Activities.Statements.If> Aktivita vyhodnotí podmínku a provede aktivitu v závislosti na výsledky tohoto vyhodnocení. Tato aktivita je velmi užitečné při použití procedurální modelování styl programování. <xref:System.Activities.Statements.If> Aktivity může být vnořena ve <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Parallel> aktivity, například. Pokud používáte <xref:System.Activities.Statements.Flowchart> aktivity, zvažte použití <xref:System.Activities.Statements.FlowDecision> aktivity místo.

## <a name="if-properties-in-the-workflow-designer"></a>Pokud vlastnosti v Návrháři pracovních postupů
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.If> vlastnosti aktivity a popisuje, jak je používat v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.If.Condition%2A>|True|Podmínku, která určuje, která podřízené aktivita se má spustit. Nastavit <xref:System.Activities.Statements.If.Condition%2A>, zadejte [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výrazu v **podmínku** pole na **Pokud** aktivity návrháře nebo v tabulce vlastností.|
|<xref:System.Activities.Statements.If.Else%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **false**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Else%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **Else** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|
|<xref:System.Activities.Statements.If.Then%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **true**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Then%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **pak** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|

## <a name="see-also"></a>Viz také

- [Pořadí](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)