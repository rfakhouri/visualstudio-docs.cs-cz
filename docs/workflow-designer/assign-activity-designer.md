---
title: Návrhář postupu provádění – Návrhář aktivity Assign
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4179c23cefbf995242288c1e778f9e0413bfe28e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993251"
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