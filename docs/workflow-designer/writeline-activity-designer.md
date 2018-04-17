---
title: Návrhář aktivity WriteLine | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b52bf3401e609076043f42a8df3544313d6e8a74
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="writeline-activity-designer"></a>Návrhář aktivity WriteLine
**WriteLine** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.WriteLine> aktivity.

## <a name="the-writeline-activity"></a>WriteLine aktivity
 <xref:System.Activities.Statements.WriteLine> Aktivity zapíše text do určeného <xref:System.IO.TextWriter> objektu. Pokud žádné <xref:System.IO.TextWriter> není zadaný, <xref:System.Activities.Statements.WriteLine> zapíše text do konzoly.

### <a name="using-the-writeline-activity-designer"></a>Pomocí návrháře WriteLine aktivity
 **WriteLine** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **WriteLine** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.WriteLine> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> WriteLine. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **WriteLine** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-writeline-properties"></a>Vlastnosti WriteLine
 Následující tabulce je zobrazena <xref:System.Activities.Statements.WriteLine> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.WriteLine> aktivity. Výchozí hodnota je WriteLine. I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít na.|
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Text pro zápis. Pokud chcete nastavit vlastnost, zadejte výraz jazyka Visual Basic v **Text** pole na **WriteLine** aktivity návrháře nebo v tabulce vlastností.|
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> Ke kterému <xref:System.Activities.Statements.WriteLine> zapíše <xref:System.Activities.Statements.WriteLine.Text%2A>. Výchozí hodnota je konzole.|

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [přiřazení](../workflow-designer/assign-activity-designer.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)