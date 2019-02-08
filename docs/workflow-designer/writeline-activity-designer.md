---
title: Návrhář postupu provádění – Návrhář aktivity WriteLine
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 17dd6e3c617749d82533d8bccb7f0caaa073ac26
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55930321"
---
# <a name="writeline-activity-designer"></a>Návrhář aktivity WriteLine

**WriteLine** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.WriteLine> aktivity.

## <a name="the-writeline-activity"></a>Aktivity WriteLine

<xref:System.Activities.Statements.WriteLine> Aktivita zapíše text do zadaného <xref:System.IO.TextWriter> objektu. Pokud ne <xref:System.IO.TextWriter> není zadána, <xref:System.Activities.Statements.WriteLine> zapíše text do konzoly.

### <a name="using-the-writeline-activity-designer"></a>Návrhář aktivity WriteLine pomocí

Přístup **WriteLine** návrháře aktivit v **primitiv** kategorii **nástrojů**. **WriteLine** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.WriteLine> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> WriteLine. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **WriteLine** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-writeline-properties"></a>Vlastnosti WriteLine

Následující tabulka ukazuje <xref:System.Activities.Statements.WriteLine> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich můžete upravit na plochu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.WriteLine> aktivity. Výchozí hodnota je WriteLine. I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem použít jeden.|
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Text pro zápis. Chcete-li nastavena vlastnost, zadejte výraz jazyka Visual Basic v **Text** pole na **WriteLine** aktivity návrháře nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> Ke kterému <xref:System.Activities.Statements.WriteLine> zapíše <xref:System.Activities.Statements.WriteLine.Text%2A>. Výchozí hodnota je konzola.|

## <a name="see-also"></a>Viz také:

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Assign](../workflow-designer/assign-activity-designer.md)
- [Delay](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)