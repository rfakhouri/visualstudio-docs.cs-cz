---
title: Návrhář aktivity compensate | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0f643770482c2d01f3f091157e63f8e987853da5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977196"
---
# <a name="compensate-activity-designer"></a>Návrhář aktivity Compensate
**Kompenzace** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Compensate> aktivity.  
  
## <a name="the-compensate-activity"></a>Aktivitu kompenzace  
 <xref:System.Activities.Statements.Compensate> Explicitně vyvolá aktivitu <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> pro aktivitu součástí <xref:System.Activities.Statements.CompensableActivity>. Pokud <xref:System.Activities.Statements.Compensate> aktivity se nepoužívá v rámci <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, nebo <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> z <xref:System.Activities.Statements.CompensableActivity>, pak je nutné zadat <xref:System.Activities.Statements.Compensate.Target%2A> vlastnost.  
  
 <xref:System.Activities.Statements.CompensationToken> Určená <xref:System.Activities.Statements.Compensate.Target%2A> zajišťuje explicitně potvrdit nebo kompenzaci <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> z <xref:System.Activities.Statements.CompensableActivity> byla úspěšně dokončena.  
  
### <a name="using-the-compensate-activity-designer"></a>Použití Návrhář aktivity Compensate  
 **Kompenzace** návrháře aktivit najdete v **transakce** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů** karty na levé straně [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Kompenzace** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Compensate> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z kompenzace. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **kompenzace** Návrhář aktivity nebo **DisplayName** pole mřížky vlastností.  
  
### <a name="the-compensate-properties"></a>Kompenzaci vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastností nebo na [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface, ale <xref:System.Activities.Statements.Compensate.Target%2A> musí být vlastnost upravit v mřížce vlastností.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.Compensate> aktivity. Výchozí hodnota je kompenzace.|  
|<xref:System.Activities.Statements.Compensate.Target%2A>|Pravda|Určuje <xref:System.Activities.InArgument%601> , který obsahuje <xref:System.Activities.Statements.CompensationToken> to <xref:System.Activities.Statements.Compensate> aktivity.|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [Aktivita CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Návrhář aktivity compensate](../workflow-designer/compensate-activity-designer.md)   
 [potvrzení](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)