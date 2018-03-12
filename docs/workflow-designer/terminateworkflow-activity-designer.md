---
title: "Návrhář aktivity TerminateWorkflow | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 683c482436e968ff9d2a1bd4ce0bbb8e173a5520
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="terminateworkflow-activity-designer"></a>Návrhář aktivity TerminateWorkflow
**TerminateWorkflow** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TerminateWorkflow> aktivity.

## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow aktivity
 <xref:System.Activities.Statements.TerminateWorkflow> Aktivity ukončí provádění pracovního postupu.

### <a name="using-the-terminateworkflow-activity-designer"></a>Pomocí návrháře TerminateWorkflow aktivity
 **TerminateWorkflow** Návrhář aktivity naleznete v **Runtime** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **TerminateWorkflow** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TerminateWorkflow> aktivitu výchozí **DisplayName** z TerminateWorkflow. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **TerminateWorkflow** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-terminateworkflow-properties"></a>Vlastnosti TerminateWorkflow
 Následující tabulce je zobrazena <xref:System.Activities.Statements.TerminateWorkflow> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.TerminateWorkflow> aktivity. Výchozí hodnota je TerminateWorkflow. I když zobrazovaný název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|Výjimka, která má být vyvolána při ukončení pracovního postupu. Tuto vlastnost lze nastavte v tabulce vlastností.|
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|Z důvodu, který vysvětluje, proč byl ukončen pracovní postup. Tuto vlastnost lze nastavte v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Modul runtime](../workflow-designer/runtime-activity-designers.md)
- [Zachovat](../workflow-designer/persist-activity-designer.md)