---
title: Návrhář aktivity InitializeCorrelation | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72778ac3757cc259019df5fb5616115f41ce0c34
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="initializecorrelation-activity-designer"></a>Návrhář aktivity InitializeCorrelation
**InitializeCorrelation** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity, která se používá k navázání korelace mezi zprávy před odesílání nebo přijímání je.

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation aktivity
 <xref:System.ServiceModel.Activities.InitializeCorrelation> Aktivita se používá k chybě při inicializaci korelací bez odesílání nebo přijímání zprávy. Korelace je obvykle inicializují při odesílání nebo přijímání zprávy. Pokud korelace je nutné vytvořit před odeslání nebo přijetí zprávy, použijte <xref:System.ServiceModel.Activities.InitializeCorrelation> k chybě při inicializaci korelaci.

### <a name="using-the-initializecorrelation-activity-designer"></a>Pomocí návrháře InitializeCorrelation aktivity
 **InitializeCorrelation** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **InitializeCorrelation** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor. Tím se vytvoří <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InitializeCorrelation.The <xref:System.Activities.Activity.DisplayName%2A> lze upravit v hlavičce **InitializeCorrelation** Návrhář aktivity nebo v  **DisplayName** pole **vlastnosti** okno.

 <xref:System.ServiceModel.Activities.CorrelationHandle> Může být určuje v **korelace** pole **vlastnosti** okno na **InitializeCorrelation** aktivity plochu návrháře.

 Kliknutím na tlačítko se třemi tečkami kromě **CorrelationData** pole **vlastnosti** okno nebo text nápovědy "Zobrazení..." na **InitializeCorrelation** Návrhář aktivity Surface zobrazí **inicializovat korelace** dialogové, ve kterém můžete zadat popisovač korelace a páry klíč hodnota použitý k inicializaci ho. Další informace o použití tohoto dialogového okna, najdete v článku [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) tématu.

### <a name="the-initializecorrelation-properties"></a>Vlastnosti InitializeCorrelation
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.InitializeCorrelation> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v **vlastnosti** okno nebo na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Výchozí hodnota je InitializeCorrelation.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít tuto hodnotu.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|<xref:System.ServiceModel.Activities.CorrelationHandle> Použité pro přidružení aktivit pracovního postupu v korelaci.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|Slovník dat korelace, která má vztah zprávy k instanci pracovního postupu.<br /><br /> Použití **inicializovat korelace** dialogové okno Konfigurace <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>. Další informace o použití toto dialogové okno, najdete v článku [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) tématu.|

## <a name="see-also"></a>Viz také

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)