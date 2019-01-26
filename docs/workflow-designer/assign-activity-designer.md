---
title: Návrhář postupu provádění – Návrhář aktivity Assign
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a9f7b695eb0ac6c29925a50b4ad346028c0ba0e4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54919483"
---
# <a name="assign-activity-designer"></a>Návrhář aktivity Assign

**Přiřadit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Assign> aktivity.

## <a name="the-assign-activity"></a>Aktivitě Assign

<xref:System.Activities.Statements.Assign> Aktivity přiřazuje hodnotu proměnné nebo argumentu.

### <a name="using-the-assign-activity-designer"></a>Návrhář aktivity Assign pomocí

**Přiřadit** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**kartu (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**Přiřadit** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění, pokud už aktivity jsou umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **přiřadit** vytvoří Návrhář aktivity <xref:System.Activities.Statements.Assign> aktivity s výchozím **DisplayName** z přiřazení. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **přiřadit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-assign-properties"></a>Přiřazení vlastnosti

Následující tabulka ukazuje <xref:System.Activities.Statements.Assign> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich můžete upravit na plochu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Assign> aktivity. Výchozí hodnota je přiřadit. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.Assign.To%2A>|Pravda|Proměnné nebo argumentu, ke kterému <xref:System.Activities.Statements.Assign.Value%2A> je přiřazen. Hodnota musí být platným identifikátorem jazyka Visual Basic. Chcete-li nastavena vlastnost, zadejte výraz jazyka Visual Basic v **k** pole na **přiřadit** aktivity návrháře nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.Assign.Value%2A>|Pravda|Hodnota, která je přiřazená k proměnné. Chcete-li nastavit <xref:System.Activities.Statements.Assign.Value%2A>, zadejte výraz jazyka Visual Basic v **hodnotu** pole na **přiřadit** aktivity návrháře nebo v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Delay](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)