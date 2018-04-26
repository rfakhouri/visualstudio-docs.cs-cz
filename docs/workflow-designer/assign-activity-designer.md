---
title: Návrhář postupu provádění – Návrhář aktivity přiřazení
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44d825d5d6ee36876c807ce067c71c1b10896623
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="assign-activity-designer"></a>Přiřadit Návrhář aktivity

**Přiřadit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Assign> aktivity.

## <a name="the-assign-activity"></a>Přiřazení aktivity

<xref:System.Activities.Statements.Assign> Aktivity přiřazuje hodnotu proměnné nebo argumentu.

### <a name="using-the-assign-activity-designer"></a>Pomocí návrháře přiřazení aktivity

**Přiřadit** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**Přiřadit** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů, kde ever aktivity jsou umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **přiřadit** vytvoří Návrhář aktivity <xref:System.Activities.Statements.Assign> aktivitu výchozí **DisplayName** z přiřazení. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **přiřadit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-assign-properties"></a>Přiřazení vlastnosti

Následující tabulce je zobrazena <xref:System.Activities.Statements.Assign> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Assign> aktivity. Výchozí hodnota je přiřadit. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.Assign.To%2A>|Hodnota TRUE|Proměnná nebo argument, ke kterému <xref:System.Activities.Statements.Assign.Value%2A> je přiřazen. Hodnota musí být platný identifikátor jazyka Visual Basic. Pokud chcete nastavit vlastnost, zadejte výraz jazyka Visual Basic v **k** pole na **přiřadit** aktivity návrháře nebo v tabulce vlastností.|
|<xref:System.Activities.Statements.Assign.Value%2A>|Hodnota TRUE|Hodnota, která je přiřazena k proměnné. Chcete-li nastavit <xref:System.Activities.Statements.Assign.Value%2A>, zadejte výraz jazyka Visual Basic v **hodnotu** pole na **přiřadit** aktivity návrháře nebo v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)