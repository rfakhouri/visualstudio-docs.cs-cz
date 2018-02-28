---
title: "Zpoždění Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 24ca658650c3b0eeb28261753b06082214cdb838
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="delay-activity-designer"></a>Návrhář aktivity zpoždění
**Zpoždění** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Delay> aktivity.  
  
## <a name="the-delay-activity"></a>Zpoždění aktivity  
 <xref:System.Activities.Statements.Delay> Aktivity zpozdí spuštění pracovního postupu pro zadanou dobu.  
  
### <a name="using-the-delay-activity-designer"></a>Pomocí návrháře prodlevy aktivity  
 **Zpoždění** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Zpoždění** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Delay> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> zpoždění. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **zpoždění** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-delay-properties"></a>Vlastnosti zpoždění  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Delay> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v tabulce vlastností a z nich můžete upravit některé na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]plochu návrháře.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Delay> aktivity. Výchozí hodnota je zpoždění. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.Delay.Duration%2A>|Hodnota TRUE|Množství času zpoždění pracovní postup. Tato vlastnost je nastavena v tabulce vlastností. Zadejte buď literál <xref:System.TimeSpan> ve formátu 00:00:00 nebo výraz jazyka Visual Basic k určení množství času.|  
  
## <a name="see-also"></a>Viz také  
 [Primitivní elementy.](../workflow-designer/primitives-activity-designers.md)   
 [Přiřazení](../workflow-designer/assign-activity-designer.md)   
 [Návrhář aktivity zpoždění](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)