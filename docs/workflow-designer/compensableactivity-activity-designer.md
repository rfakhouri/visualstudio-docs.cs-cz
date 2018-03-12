---
title: "Návrhář aktivity CompensableActivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c45a0f2638a3d1fc5b6f4dc536cf051751c9c897
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="compensableactivity-activity-designer"></a>Návrhář aktivity CompensableActivity
**CompensableActivity** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CompensableActivity> aktivity.

## <a name="the-compensableactivity-activity"></a>CompensableActivity aktivity
 <xref:System.Activities.Statements.CompensableActivity> Definuje jednotky práce, která může být potvrzen nebo kompenzované po úspěšném dokončení.

### <a name="using-the-compensableactivity-activity-designer"></a>Pomocí návrháře CompensableActivity aktivity
 **CompensableActivity** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **CompensableActivity** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.CompensableActivity> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z CompensableActivity. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **CompensableActivity** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-compensableactivity-properties"></a>Vlastnosti CompensableActivity
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CompensableActivity> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> a <xref:System.Activities.Activity%601.Result%2A> vlastnost lze upravit v tabulce vlastností, ale ostatní vlastnosti musí být upravovat na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.CompensableActivity> aktivity. Výchozí hodnota je CompensableActivity.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Určuje, vrátí hodnotu, která <xref:System.Activities.Statements.CompensableActivity>. Tato vlastnost je nutné upravit v tabulce vlastností.|
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|True|Určuje aktivitu, pro který je k dispozici logice kompenzace, zrušení a potvrzení. Chcete-li přidat <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **CompensableActivity** Návrhář aktivity s textem pomocný parametr "rozevírací aktivity sem".|
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|Určuje aktivity, která se spustí v případě zrušení. Chcete-li přidat aktivitu, vyřaďte jeho designer z **sada nástrojů** do **CancellationHandler** pole na **CompensableActivity** Návrhář aktivity s textem pomocný parametr "rozevírací Aktivity sem".|
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|Určuje aktivity budou spuštěny při kompenzace <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity. Tuto obslužnou rutinu nelze explicitně vyvolat pomocí <xref:System.Activities.Statements.Compensate> aktivity.<br /><br /> Chcete-li přidat aktivitu, vyřaďte jeho Návrhář aktivity z **sada nástrojů** do **CompensationHandler** pole na **CompensableActivity** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|Určuje aktivity budou spuštěny při potvrzení <xref:System.Activities.Statements.CompensableActivity.Body%2A> aktivity. Tuto obslužnou rutinu nelze explicitně vyvolat pomocí <xref:System.Activities.Statements.Confirm> aktivity.<br /><br /> Chcete-li přidat aktivitu, vyřaďte jeho Návrhář aktivity z **sada nástrojů** do **ConfirmationHandler** pole na **CompensableActivity** Návrhář aktivity s textem pomocný parametr " Aktivity sem umístěte".|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)