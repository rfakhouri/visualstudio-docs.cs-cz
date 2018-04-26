---
title: Návrhář postupu provádění - CancellationScope Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0f9a40434821294384154ddcbbfebbd0a7885eb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="cancellationscope-activity-designer"></a>Návrhář aktivity CancellationScope

**CancellationScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CancellationScope> aktivity.

## <a name="the-cancellationscope-activity"></a>CancellationScope aktivity
 <xref:System.Activities.Statements.CancellationScope> Aktivitu můžete zadat aktivitu pro spouštění a zrušení logiku pro danou aktivitu.

### <a name="using-the-cancellationscope-activity-designer"></a>Pomocí návrháře CancellationScope aktivity
 **CancellationScope** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**. Otevřete **sada nástrojů**, vyberte **sada nástrojů** kartě návrháře pracovních postupů. Případně vyberte možnost **nástrojů** z **zobrazení** nabídce nebo stiskněte klávesu CTRL + ALT + X.

 **CancellationScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **CancellationScope** vytvoří Návrhář aktivity <xref:System.Activities.Statements.CancellationScope> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z CancellationScope. Upravit <xref:System.Activities.Activity.DisplayName%2A> hodnota v hlavičce **CancellationScope** Návrhář aktivity. Můžete také upravit ho **DisplayName** pole mřížku vlastností.

### <a name="the-cancellationscope-properties"></a>Vlastnosti CancellationScope
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v tabulce vlastností ale musí být ostatní vlastnosti upravovat na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je CancellationScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Hodnota TRUE|Určuje aktivity, pro které zrušení logiku poskytnuty. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **CancellationScope** Návrhář aktivity. Přidejte text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Hodnota TRUE|Určuje aktivity, která se spustí, pokud dojde zrušení. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **CancellationHandler** pole na **CancellationScope** Návrhář aktivity. Přidejte text nápovědy "Aktivity Sem přetáhněte".|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)