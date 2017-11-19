---
title: "Návrhář aktivity TerminateWorkflow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a3b7c7cf56aa465f88ae918056e2d71ad6c41e4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
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
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)   
 [Zachovat](../workflow-designer/persist-activity-designer.md)