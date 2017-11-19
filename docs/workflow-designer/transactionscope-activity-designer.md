---
title: "Návrhář aktivity TransactionScope | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1f5d948171b78c9d9e5b42cefcf5b051faf20c78
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="transactionscope-activity-designer"></a>Návrhář aktivity TransactionScope
**TransactionScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TransactionScope> aktivity.  
  
## <a name="the-transactionscope-activity"></a>TransactionScope aktivity  
 <xref:System.Activities.Statements.TransactionScope> Aktivita provádí aktivity obsažené v rámci jedné transakce. Transakce potvrdí, kdy <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity a všechny ostatní účastníci transakce byly úspěšně dokončeny.  
  
### <a name="using-the-transactionscope-activity-designer"></a>Pomocí návrháře TransactionScope aktivity  
 **TransactionScope** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **TransactionScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TransactionScope> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z TransactionScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **TransactionScope** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-transactionscope-properties"></a>Vlastnosti TransactionScope  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.TransactionScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Statements.TransactionScope.Body%2A> vlastnosti můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor. Ale ostatní vlastnosti musí být upravovat na mřížku vlastností.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.TransactionScope> aktivity. Výchozí hodnota je TransactionScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|Hodnota TRUE|Určuje aktivity provést v rámci jedné transakce. Chcete-li přidat <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **TransactionScope** Návrhář aktivity s text nápovědy "aktivity rozevírací Zde".|  
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|Hodnota TRUE|Určuje, <xref:System.Transactions.IsolationLevel> pro tento <xref:System.Activities.Statements.TransactionScope>.|  
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Určuje interval času (ve formátu jako 00:00:00, který označuje čas: minuty: sekundy) s k dokončení transakce. Výchozí hodnota je 1 minuta (00: 01:00).|  
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|Hodnota TRUE|Určuje hodnotu, která určuje, zda by měl pracovní postup zrušit, pokud zruší transakce.|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Kompenzace](../workflow-designer/compensate-activity-designer.md)   
 [Potvrďte](../workflow-designer/confirm-activity-designer.md)