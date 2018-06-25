---
title: Návrhář postupu provádění - TransactionScope Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7622dc9b926124d0ed2b2ae759beafcbac3a475a
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755795"
---
# <a name="transactionscope-activity-designer"></a>Návrhář aktivity TransactionScope

**TransactionScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.TransactionScope> aktivity.

## <a name="the-transactionscope-activity"></a>TransactionScope aktivity

<xref:System.Activities.Statements.TransactionScope> Aktivita provádí aktivity obsažené v rámci jedné transakce. Transakce potvrdí, kdy <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity a všechny ostatní účastníci transakce byly úspěšně dokončeny.

### <a name="using-the-transactionscope-activity-designer"></a>Pomocí návrháře TransactionScope aktivity

Přístup **TransactionScope** Návrhář aktivity v **transakce** kategorii **sada nástrojů**. **TransactionScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.TransactionScope> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z TransactionScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **TransactionScope** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-transactionscope-properties"></a>Vlastnosti TransactionScope

Následující tabulce je zobrazena <xref:System.Activities.Statements.TransactionScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Statements.TransactionScope.Body%2A> vlastnosti můžete upravit na plochu návrháře pracovních postupů. Ale ostatní vlastnosti musí být upravovat na mřížku vlastností.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.TransactionScope> aktivity. Výchozí hodnota je TransactionScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|Hodnota TRUE|Určuje aktivity provést v rámci jedné transakce. Chcete-li přidat <xref:System.Activities.Statements.TransactionScope.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **TransactionScope** Návrhář aktivity s text nápovědy "aktivity rozevírací Zde".|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|Hodnota TRUE|Určuje, <xref:System.Transactions.IsolationLevel> pro tento <xref:System.Activities.Statements.TransactionScope>.|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Určuje interval času (ve formátu jako 00:00:00, který označuje čas: minuty: sekundy) s k dokončení transakce. Výchozí hodnota je 1 minuta (00: 01:00).|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|Hodnota TRUE|Určuje hodnotu, která určuje, zda by měl pracovní postup zrušit, pokud zruší transakce.|

## <a name="see-also"></a>Viz také:

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)