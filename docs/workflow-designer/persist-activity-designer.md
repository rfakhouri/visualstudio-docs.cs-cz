---
title: "Zachovat Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fa7868d814b1ee5079cba69b9d54665ad1e4a47
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="persist-activity-designer"></a>Zachovat Návrhář aktivity
**Zachovat** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Persist> aktivity.  
  
## <a name="the-persist-activity"></a>Zachovat aktivity  
 <xref:System.Activities.Statements.Persist> Aktivity uloží pracovní postup na disk, pokud je to možné. <xref:System.Activities.Statements.Persist> Aktivitu nelze provést v zóně bez trvalost jako je například uvnitř <xref:System.Activities.Statements.TransactionScope> aktivity. Pokud použijete <xref:System.Activities.Statements.Persist> aktivity v jiných trvalost oboru, je vyvolána výjimka za běhu.  
  
### <a name="using-the-persist-activity-designer"></a>Pomocí zachovat Návrhář aktivity  
 **Zachovat** Návrhář aktivity naleznete v **Runtime** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů** Karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Zachovat** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Persist> aktivitu výchozí **DisplayName** trvalého. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **zachovat** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-persist-properties"></a>Zachovat vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Persist> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Persist> aktivity. Výchozí hodnota je zachovat. I když zobrazovaný název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|  
  
## <a name="see-also"></a>Viz také  
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)