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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 81caba883293a59fe67988d34785758340b4705a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54987034"
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