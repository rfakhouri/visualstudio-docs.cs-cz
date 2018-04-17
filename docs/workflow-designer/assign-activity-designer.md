---
title: Přiřadit Návrhář aktivity | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e5992420bb83323525e0b36bbc7d3b383ca9a3a2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assign-activity-designer"></a>Přiřadit Návrhář aktivity
**Přiřadit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Assign> aktivity.

## <a name="the-assign-activity"></a>Přiřazení aktivity
 <xref:System.Activities.Statements.Assign> Aktivity přiřazuje hodnotu proměnné nebo argumentu.

### <a name="using-the-assign-activity-designer"></a>Pomocí návrháře přiřazení aktivity
 **Přiřadit** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Přiřadit** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kde je to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Assign> aktivitu výchozí **DisplayName** z přiřazení. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **přiřadit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-assign-properties"></a>Přiřazení vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Assign> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Assign> aktivity. Výchozí hodnota je přiřadit. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.Assign.To%2A>|Hodnota TRUE|Proměnná nebo argument, ke kterému <xref:System.Activities.Statements.Assign.Value%2A> je přiřazen. Toto musí být platný identifikátor jazyka Visual Basic. Pokud chcete nastavit vlastnost, zadejte výraz jazyka Visual Basic v **k** pole na **přiřadit** aktivity návrháře nebo v tabulce vlastností.|
|<xref:System.Activities.Statements.Assign.Value%2A>|Hodnota TRUE|Hodnota, která je přiřazena k proměnné. Chcete-li nastavit <xref:System.Activities.Statements.Assign.Value%2A>, zadejte výraz jazyka Visual Basic v **hodnotu** pole na **přiřadit** aktivity návrháře nebo v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)