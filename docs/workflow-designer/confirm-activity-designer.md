---
title: Návrhář postupu provádění - Potvrďte Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Confirm.UI
ms.assetid: c753b67b-b0e7-462a-bb4e-ba8db04a078d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21a4c1b31769387470d58f27a060d4e3ec7ae70c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="confirm-activity-designer"></a>Potvrďte Návrhář aktivity

**Potvrdit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Confirm> aktivity.

## <a name="the-confirm-activity"></a>Potvrzení aktivity
 <xref:System.Activities.Statements.Confirm> Explicitně vyvolá aktivitu <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> pro aktivitu součástí <xref:System.Activities.Statements.CompensableActivity>. Pokud <xref:System.Activities.Statements.Confirm> aktivity se nepoužívá v rámci <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, nebo <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> z <xref:System.Activities.Statements.CompensableActivity>, pak je nutné zadat <xref:System.Activities.Statements.Confirm.Target%2A> vlastnost.

 <xref:System.Activities.Statements.CompensationToken> Určeným elementem <xref:System.Activities.Statements.Compensate.Target%2A> poskytuje prostředky ke explicitně potvrdit nebo odpovídajícím způsobem <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> z <xref:System.Activities.Statements.CompensableActivity> bylo úspěšně dokončeno.

### <a name="using-the-confirm-activity-designer"></a>Pomocí Potvrďte Návrhář aktivity
 **Potvrdit** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně návrháře pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Potvrdit** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Confirm> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> o potvrzení. <xref:System.Activities.Activity.DisplayName%2A> Hodnota může být buď v hlavičce upravit **potvrdit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-confirm-properties"></a>Potvrzení vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Confirm> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastnost nebo na plochu návrháře pracovních postupů, ale <xref:System.Activities.Statements.Confirm.Target%2A> vlastnost musí upravit v tabulce vlastností.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je potvrdit.|
|<xref:System.Activities.Statements.Confirm.Target%2A>|Hodnota TRUE|Určuje, <xref:System.Activities.InArgument%601> obsahující <xref:System.Activities.Statements.CompensationToken> pro tento <xref:System.Activities.Statements.Confirm> aktivity.|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)