---
title: Návrhář postupu provádění - odpovídajícím způsobem Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8278066a12df0d195770391d0b2f3144ba16487d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31972264"
---
# <a name="compensate-activity-designer"></a>Odpovídajícím způsobem Návrhář aktivity

**Compensate** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Compensate> aktivity.

## <a name="the-compensate-activity"></a>Odpovídajícím způsobem aktivity
 <xref:System.Activities.Statements.Compensate> Explicitně vyvolá aktivitu <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> pro aktivitu součástí <xref:System.Activities.Statements.CompensableActivity>. Pokud <xref:System.Activities.Statements.Compensate> aktivity se nepoužívá v rámci <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, nebo <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> z <xref:System.Activities.Statements.CompensableActivity>, pak je nutné zadat <xref:System.Activities.Statements.Compensate.Target%2A> vlastnost.

 <xref:System.Activities.Statements.CompensationToken> Určeným elementem <xref:System.Activities.Statements.Compensate.Target%2A> poskytuje prostředky ke explicitně potvrdit nebo odpovídajícím způsobem <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> z <xref:System.Activities.Statements.CompensableActivity> bylo úspěšně dokončeno.

### <a name="using-the-compensate-activity-designer"></a>Pomocí odpovídajícím způsobem Návrhář aktivity
 **Compensate** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**. Otevřete **sada nástrojů**, vyberte **sada nástrojů** karty na levé straně návrháře pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení**nabídky nebo CTRL + ALT + X.)

 **Compensate** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.Compensate> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z Compensate. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **Compensate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-compensate-properties"></a>Odpovídajícím způsobem vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastnost nebo na plochu návrháře pracovních postupů. Upravit <xref:System.Activities.Statements.Compensate.Target%2A> vlastnost v tabulce vlastností.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Compensate> aktivity. Výchozí hodnota je Compensate.|
|<xref:System.Activities.Statements.Compensate.Target%2A>|Hodnota TRUE|Určuje, <xref:System.Activities.InArgument%601> obsahující <xref:System.Activities.Statements.CompensationToken> pro tento <xref:System.Activities.Statements.Compensate> aktivity.|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Návrhář aktivity Compensate](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)