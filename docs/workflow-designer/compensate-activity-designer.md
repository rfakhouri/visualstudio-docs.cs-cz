---
title: "Odpovídajícím způsobem Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 7d6317299bef78b4f5ee882bcf8d1353b81b5100
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="compensate-activity-designer"></a>Odpovídajícím způsobem Návrhář aktivity
**Compensate** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Compensate> aktivity.  
  
## <a name="the-compensate-activity"></a>Odpovídajícím způsobem aktivity  
 <xref:System.Activities.Statements.Compensate> Explicitně vyvolá aktivitu <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> pro aktivitu součástí <xref:System.Activities.Statements.CompensableActivity>. Pokud <xref:System.Activities.Statements.Compensate> aktivity se nepoužívá v rámci <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, nebo <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> z <xref:System.Activities.Statements.CompensableActivity>, pak je nutné zadat <xref:System.Activities.Statements.Compensate.Target%2A> vlastnost.  
  
 <xref:System.Activities.Statements.CompensationToken> Určeným elementem <xref:System.Activities.Statements.Compensate.Target%2A> poskytuje prostředky ke explicitně potvrdit nebo odpovídajícím způsobem <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> z <xref:System.Activities.Statements.CompensableActivity> bylo úspěšně dokončeno.  
  
### <a name="using-the-compensate-activity-designer"></a>Pomocí odpovídajícím způsobem Návrhář aktivity  
 **Compensate** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Compensate** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Compensate> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z Compensate. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **Compensate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-compensate-properties"></a>Odpovídajícím způsobem vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastnost nebo na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor, ale <xref:System.Activities.Statements.Compensate.Target%2A> vlastnost musí upravit v tabulce vlastností.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Compensate> aktivity. Výchozí hodnota je Compensate.|  
|<xref:System.Activities.Statements.Compensate.Target%2A>|Hodnota TRUE|Určuje, <xref:System.Activities.InArgument%601> obsahující <xref:System.Activities.Statements.CompensationToken> pro tento <xref:System.Activities.Statements.Compensate> aktivity.|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Odpovídajícím způsobem Návrhář aktivity](../workflow-designer/compensate-activity-designer.md)   
 [Potvrďte](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)