---
title: "Pokud návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3d3928330558c3d611decd2a87498d33fd6482ce
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="if-activity-designer"></a>Pokud návrhář aktivity
<xref:System.Activities.Statements.If> Aktivita vyhodnotí podmínku a provede aktivitu v závislosti na výsledky tohoto vyhodnocení. Tato aktivita je velmi užitečné při použití procedurální modelování styl programování. <xref:System.Activities.Statements.If> Aktivity může být vnořena ve <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Parallel> aktivity, například. Pokud používáte <xref:System.Activities.Statements.Flowchart> aktivity, zvažte použití <xref:System.Activities.Statements.FlowDecision> aktivity místo.  
  
## <a name="if-properties-in-the-workflow-designer"></a>Pokud vlastnosti v Návrháři pracovních postupů  
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.If> vlastnosti aktivity a popisuje, jak je používat v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.If.Condition%2A>|Hodnota TRUE|Podmínku, která určuje, která podřízené aktivita se má spustit. Nastavit <xref:System.Activities.Statements.If.Condition%2A>, zadejte [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výrazu v **podmínku** pole na **Pokud** aktivity návrháře nebo v tabulce vlastností.|  
|<xref:System.Activities.Statements.If.Else%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **false**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Else%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **Else** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|  
|<xref:System.Activities.Statements.If.Then%2A>|False|Aktivitu spustit, pokud <xref:System.Activities.Statements.If.Condition%2A> je **true**. Chcete-li přidat aktivitu, která spouští <xref:System.Activities.Statements.If.Then%2A> větev, vyřaďte aktivitu z **sada nástrojů** do **pak** pole na **Pokud** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|  
  
## <a name="see-also"></a>Viz také  
 [Pořadí](../workflow-designer/sequence-activity-designer.md)   
 [Paralelní](../workflow-designer/parallel-activity-designer.md)   
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)