---
title: Návrhář postupu provádění - CompensableActivity Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fdab42766fd20989831e446a45115d17b3ee28fd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31978658"
---
# <a name="compensableactivity-activity-designer"></a>Návrhář aktivity CompensableActivity

**CompensableActivity** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CompensableActivity> aktivity.

## <a name="the-compensableactivity-activity"></a>CompensableActivity aktivity
 <xref:System.Activities.Statements.CompensableActivity> Definuje jednotky práce, která může být potvrzen nebo kompenzované po úspěšném dokončení.

### <a name="using-the-compensableactivity-activity-designer"></a>Pomocí návrháře CompensableActivity aktivity
 **CompensableActivity** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**. Otevřete **sada nástrojů**, vyberte **sada nástrojů** karty na levé straně návrháře pracovních postupů. Případně vyberte možnost **nástrojů** z **zobrazení** nabídce nebo stiskněte klávesu CTRL + ALT + X.

 **CompensableActivity** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů. Návrhář aktivity uvnitř může vyřadit <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.CompensableActivity> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z CompensableActivity. Upravit <xref:System.Activities.Activity.DisplayName%2A> hodnota v hlavičce **CompensableActivity** Návrhář aktivity. Také se dá upravit v **DisplayName** pole mřížku vlastností.

### <a name="the-compensableactivity-properties"></a>Vlastnosti CompensableActivity
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CompensableActivity> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Activity%601.Result%2A> vlastnost lze upravit v tabulce vlastností ale musí být ostatní vlastnosti upravovat na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.CompensableActivity> aktivity. Výchozí hodnota je CompensableActivity.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Určuje, vrátí hodnotu, která <xref:System.Activities.Statements.CompensableActivity>. Tato vlastnost je nutné upravit v tabulce vlastností.|
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|Hodnota TRUE|Určuje aktivitu, pro který je k dispozici logice kompenzace, zrušení a potvrzení. Chcete-li přidat <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **CompensableActivity** Návrhář aktivity. Přidejte pomocný parametr text "Sem rozevírací aktivita".|
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|Určuje aktivity, která se spustí, když dojde zrušení. Chcete-li přidat aktivitu, vyřaďte jeho designer z **sada nástrojů** do **CancellationHandler** pole na **CompensableActivity** Návrhář aktivity. Přidejte text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|Určuje aktivity budou spuštěny při kompenzace <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity. Tuto obslužnou rutinu nelze explicitně vyvolat pomocí <xref:System.Activities.Statements.Compensate> aktivity.<br /><br /> Chcete-li přidat aktivitu, vyřaďte jeho Návrhář aktivity z **sada nástrojů** do **CompensationHandler** pole na **CompensableActivity** Návrhář aktivity. Přidejte text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|Určuje aktivity budou spuštěny při potvrzení <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity. Tuto obslužnou rutinu nelze explicitně vyvolat pomocí <xref:System.Activities.Statements.Confirm> aktivity.<br /><br /> Chcete-li přidat aktivitu, vyřaďte jeho Návrhář aktivity z **sada nástrojů** do **ConfirmationHandler** pole na **CompensableActivity** Návrhář aktivity. Přidejte text nápovědy "Aktivity Sem přetáhněte".|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)