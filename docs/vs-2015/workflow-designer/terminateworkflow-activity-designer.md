---
title: Návrhář aktivity Terminateworkflow | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b471cee4a07722e37ae4b58817823dd4fa48ee26
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767832"
---
# <a name="terminateworkflow-activity-designer"></a>Návrhář aktivity TerminateWorkflow
**TerminateWorkflow** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TerminateWorkflow> aktivity.  
  
## <a name="the-terminateworkflow-activity"></a>Aktivity TerminateWorkflow  
 <xref:System.Activities.Statements.TerminateWorkflow> Aktivity ukončí provádění pracovního postupu.  
  
### <a name="using-the-terminateworkflow-activity-designer"></a>Pomocí aktivity Terminateworkflow  
 **TerminateWorkflow** návrháře aktivit najdete v **Runtime** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů** kartu (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **TerminateWorkflow** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TerminateWorkflow> aktivity s výchozím **DisplayName** z TerminateWorkflow. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **TerminateWorkflow** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-terminateworkflow-properties"></a>Vlastnosti TerminateWorkflow  
 Následující tabulka ukazuje <xref:System.Activities.Statements.TerminateWorkflow> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich bylo možné upravovat ve [!INCLUDE[wfd2](../includes/wfd2-md.md)] povrchu.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.TerminateWorkflow> aktivity. Výchozí hodnota je TerminateWorkflow. I když zobrazovaný název není bezpodmínečně nutné, je osvědčeným postupem použít zobrazovaný název.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|Výjimka, která má být vyvolána při ukončení pracovního postupu. Tuto vlastnost nastavte v mřížce vlastností.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|Proč se vysvětluje, proč byl ukončen pracovní postup. Tuto vlastnost nastavte v mřížce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)   
 [Persist](../workflow-designer/persist-activity-designer.md)