---
title: Návrhář postupu provádění - při návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c75ce30ba231efa9084ce6ec733f08c5b86aa861
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987755"
---
# <a name="while-activity-designer"></a>Návrhář aktivity While

<xref:System.Activities.Statements.While> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.While.Body%2A> while zadaný <xref:System.Activities.Statements.While.Condition%2A> vyhodnotí jako **true**. Nikdy může spustit obsaženou aktivitu. Pokud chcete obsažené aktivity na minimálně jednou provedeno, použijte <xref:System.Activities.Statements.DoWhile> aktivity místo.

## <a name="while-properties-in-workflow-designer"></a>Zatímco vlastnosti v Návrháři postupu provádění

V následující tabulce jsou uvedeny nejužitečnější <xref:System.Activities.Statements.While> vlastnosti aktivit a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.While> návrháře aktivit v záhlaví. Výchozí hodnota je při. Hodnotu lze upravit v **vlastnosti** okno nebo přímo v hlavičce návrháře aktivit.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.While.Body%2A>|False|Obsahuje aktivity ke spuštění během <xref:System.Activities.Statements.While.Condition%2A> vyhodnotí jako **true**.|
|<xref:System.Activities.Statements.While.Condition%2A>|Pravda|Obsahuje výraz jazyka Visual Basic, který je vyhodnocován pro určení, zda aktivitu v <xref:System.Activities.Statements.While.Body%2A> má být provedena.|

## <a name="see-also"></a>Viz také:

- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)
- [DoWhile](../workflow-designer/dowhile-activity-designer.md)