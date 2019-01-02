---
title: Návrhář postupu provádění – Návrhář aktivity TransactionScope
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e823ea0fa716545dcc2cfba3df3ba93118e65f6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53873710"
---
# <a name="transactionscope-activity-designer"></a>Návrhář aktivity TransactionScope

**TransactionScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TransactionScope> aktivity.

## <a name="the-transactionscope-activity"></a>Aktivity TransactionScope

<xref:System.Activities.Statements.TransactionScope> Aktivity spustí obsaženou aktivitu v rámci jedné transakce. Potvrzení transakce, kdy <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity a všechny ostatní účastníci transakce byly úspěšně dokončeny.

### <a name="using-the-transactionscope-activity-designer"></a>Pomocí návrháře aktivity TransactionScope

Přístup **TransactionScope** návrháře aktivit v **transakce** kategorii **nástrojů**. **TransactionScope** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TransactionScope> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> TransactionScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **TransactionScope** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností.

### <a name="the-transactionscope-properties"></a>Vlastnosti objektu TransactionScope

Následující tabulka ukazuje <xref:System.Activities.Statements.TransactionScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Statements.TransactionScope.Body%2A> na plochu návrháře postupu provádění můžete upravit vlastnosti. Ale další vlastnosti nutné upravit v mřížce vlastností.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.Activities.Statements.TransactionScope> aktivity. Výchozí hodnota je objekt TransactionScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|Pravda|Určuje aktivity ke spuštění v rámci jedné transakce. Chcete-li přidat <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity, rozevírací aktivitu z **nástrojů** do **text** pole na **TransactionScope** Návrhář aktivity s text nápovědy "přetáhněte aktivitu sem".|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|Pravda|Určuje, <xref:System.Transactions.IsolationLevel> to <xref:System.Activities.Statements.TransactionScope>.|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Určuje dobu (ve formátu jako 00:00:00, který označuje hodiny: minuty: sekundy), který má k dokončení transakce. Výchozí hodnota je 1 minuta (00: 01:00).|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|Pravda|Určuje hodnotu, která určuje, zda pracovní postup by měl být zrušen Pokud přerušení transakce.|

## <a name="see-also"></a>Viz také:

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)