---
title: Návrhář postupu provádění – Návrhář aktivity zpoždění
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31b632177ba941ad0e5ddb5700ae430573fd817d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758450"
---
# <a name="delay-activity-designer"></a>Návrhář aktivity Delay

**Zpoždění** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Delay> aktivity.

## <a name="the-delay-activity"></a>Zpoždění aktivity

<xref:System.Activities.Statements.Delay> Aktivity zpozdí spuštění pracovního postupu pro zadanou dobu.

### <a name="use-the-delay-activity-designer"></a>Použití Návrhář aktivity zpoždění

**Zpoždění** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**kartě návrháře pracovních postupů. Případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky, nebo klikněte na tlačítko **Ctrl**+**Alt** + **X**.

**Zpoždění** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.Delay> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> zpoždění. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **zpoždění** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-delay-properties"></a>Vlastnosti zpoždění

Následující tabulce je zobrazena <xref:System.Activities.Statements.Delay> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v tabulce vlastností a některá z nich můžete upravit na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Delay> aktivity. Výchozí hodnota je zpoždění. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|Hodnota TRUE|Množství času zpoždění pracovní postup. Tato vlastnost je nastavena v tabulce vlastností. Zadejte buď literál <xref:System.TimeSpan> ve formátu 00:00:00 nebo výraz jazyka Visual Basic k určení množství času.|

## <a name="see-also"></a>Viz také:

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Přiřazení](../workflow-designer/assign-activity-designer.md)
- [Návrhář aktivity Delay](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)