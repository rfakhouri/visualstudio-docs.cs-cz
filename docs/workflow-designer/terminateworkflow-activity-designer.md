---
title: Návrhář postupu provádění - TerminateWorkflow Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5dfd7438a14f0bcbedcf5cdc5add78020604c355
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975556"
---
# <a name="terminateworkflow-activity-designer"></a>Návrhář aktivity TerminateWorkflow

**TerminateWorkflow** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TerminateWorkflow> aktivity.

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow aktivity

<xref:System.Activities.Statements.TerminateWorkflow> Aktivity ukončí provádění pracovního postupu.

### <a name="using-the-terminateworkflow-activity-designer"></a>Pomocí návrháře TerminateWorkflow aktivity

**TerminateWorkflow** Návrhář aktivity naleznete v **Runtime** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**TerminateWorkflow** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TerminateWorkflow> aktivitu výchozí **DisplayName** z TerminateWorkflow. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **TerminateWorkflow** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-terminateworkflow-properties"></a>Vlastnosti TerminateWorkflow

Následující tabulce je zobrazena <xref:System.Activities.Statements.TerminateWorkflow> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.TerminateWorkflow> aktivity. Výchozí hodnota je TerminateWorkflow. I když zobrazovaný název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|Výjimka, která má být vyvolána při ukončení pracovního postupu. Tuto vlastnost lze nastavte v tabulce vlastností.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|Z důvodu, který vysvětluje, proč byl ukončen pracovní postup. Tuto vlastnost lze nastavte v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Modul runtime](../workflow-designer/runtime-activity-designers.md)
- [Zachovat](../workflow-designer/persist-activity-designer.md)