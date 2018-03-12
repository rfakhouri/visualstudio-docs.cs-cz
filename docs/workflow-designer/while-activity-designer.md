---
title: "Při Návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 541113e598246cf20f9fe625f57c51f68d7e9ca8
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="while-activity-designer"></a>Při Návrhář aktivity
<xref:System.Activities.Statements.While> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.While.Body%2A> při zadaný <xref:System.Activities.Statements.While.Condition%2A> vyhodnotí jako **true**. Obsažené aktivity nikdy může spustit. Pokud chcete obsažené aktivitu aspoň jednou provést, použijte <xref:System.Activities.Statements.DoWhile> aktivity místo.

## <a name="while-properties-in-workflow-designer"></a>Při vlastnosti v Návrháři pracovních postupů
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.While> vlastnosti aktivity a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.While> Návrhář aktivity v hlavičce. Výchozí hodnota je při. Hodnotu lze upravit v **vlastnosti** okno nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.While.Body%2A>|False|Obsahuje aktivitu provést při <xref:System.Activities.Statements.While.Condition%2A> vyhodnotí jako **true**.|
|<xref:System.Activities.Statements.While.Condition%2A>|True|Obsahuje [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výraz, který se vyhodnotí k určení zda aktivity v <xref:System.Activities.Statements.While.Body%2A> má být provedena.|

## <a name="see-also"></a>Viz také

- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)