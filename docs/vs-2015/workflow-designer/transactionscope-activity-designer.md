---
title: Návrhář aktivity TransactionScope | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: abed15a1ce3d406cfd5e95318dd332a677f61095
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976542"
---
# <a name="transactionscope-activity-designer"></a>Návrhář aktivity TransactionScope
**TransactionScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TransactionScope> aktivity.  
  
## <a name="the-transactionscope-activity"></a>Aktivity TransactionScope  
 <xref:System.Activities.Statements.TransactionScope> Aktivity spustí obsaženou aktivitu v rámci jedné transakce. Potvrzení transakce, kdy <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity a všechny ostatní účastníci transakce byly úspěšně dokončeny.  
  
### <a name="using-the-transactionscope-activity-designer"></a>Pomocí návrháře aktivity TransactionScope  
 **TransactionScope** návrháře aktivit najdete v **transakce** kategorii **nástrojů**, který přistupuje po kliknutí **sady nástrojů**  kartě [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **TransactionScope** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TransactionScope> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> TransactionScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **TransactionScope** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností.  
  
### <a name="the-transactionscope-properties"></a>Vlastnosti objektu TransactionScope  
 Následující tabulka ukazuje <xref:System.Activities.Statements.TransactionScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Statements.TransactionScope.Body%2A> lze upravit na [!INCLUDE[wfd2](../includes/wfd2-md.md)] povrchu. Ale další vlastnosti nutné upravit v mřížce vlastností.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.Activities.Statements.TransactionScope> aktivity. Výchozí hodnota je objekt TransactionScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|Pravda|Určuje aktivity ke spuštění v rámci jedné transakce. Chcete-li přidat <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity, rozevírací aktivitu z **nástrojů** do **text** pole na **TransactionScope** Návrhář aktivity s text nápovědy "přetáhněte aktivitu sem".|  
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|Pravda|Určuje, <xref:System.Transactions.IsolationLevel> to <xref:System.Activities.Statements.TransactionScope>.|  
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Určuje dobu (ve formátu jako 00:00:00, který označuje hodiny: minuty: sekundy), který má k dokončení transakce. Výchozí hodnota je 1 minuta (00: 01:00).|  
|<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure?qualifyHint=False&autoUpgrade=True>|Pravda|Určuje hodnotu, která určuje, zda pracovní postup by měl být zrušen Pokud přerušení transakce.|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)   
 [Aktivita CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Kompenzace](../workflow-designer/compensate-activity-designer.md)   
 [Confirm](../workflow-designer/confirm-activity-designer.md)