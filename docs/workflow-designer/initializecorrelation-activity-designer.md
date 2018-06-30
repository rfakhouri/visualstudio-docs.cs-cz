---
title: Návrhář postupu provádění - InitializeCorrelation Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b210b5e0d3d0f3638e78331d9db093f7e86079e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117170"
---
# <a name="initializecorrelation-activity-designer"></a>Návrhář aktivity InitializeCorrelation

**InitializeCorrelation** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. <xref:System.ServiceModel.Activities.InitializeCorrelation> Aktivita vytváří korelace mezi zprávy před odesílání nebo přijímání je.

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation aktivity

<xref:System.ServiceModel.Activities.InitializeCorrelation> Aktivita se používá k chybě při inicializaci korelací bez odesílání nebo přijímání zprávy. Korelace je obvykle inicializují při odesílání nebo přijímání zprávy. Pokud korelace je nutné vytvořit před odeslání nebo přijetí zprávy, použijte <xref:System.ServiceModel.Activities.InitializeCorrelation> k chybě při inicializaci korelaci.

### <a name="using-the-initializecorrelation-activity-designer"></a>Pomocí návrháře InitializeCorrelation aktivity

Přístup **InitializeCorrelation** Návrhář aktivity v **zasílání zpráv** kategorii **sada nástrojů**.

**InitializeCorrelation** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů. Vyřazení Návrhář aktivity vytvoří <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InitializeCorrelation. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **InitializeCorrelation** Návrhář aktivity nebo v **DisplayName** pole **vlastnosti** okno.

<xref:System.ServiceModel.Activities.CorrelationHandle> Může být určuje v **korelace** pole **vlastnosti** okno na **InitializeCorrelation** aktivity plochu návrháře.

Chcete-li zobrazit **inicializovat korelace** dialogové, kde můžete určit popisovač korelace a páry klíč hodnota používá k chybě při inicializaci, vyberte tlačítko se třemi tečkami vedle **CorrelationData** pole **vlastnosti** okno. Nebo vyberte text nápovědy "Zobrazení..." na **InitializeCorrelation** aktivity plochu návrháře. Další informace o použití tohoto dialogového okna, najdete v článku [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) článku.

### <a name="the-initializecorrelation-properties"></a>Vlastnosti InitializeCorrelation

Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.InitializeCorrelation> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v **vlastnosti** okno nebo na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Výchozí hodnota je InitializeCorrelation.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> není nezbytně nutné, doporučujeme.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|<xref:System.ServiceModel.Activities.CorrelationHandle> Použité pro přidružení aktivit pracovního postupu v korelaci.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|Slovník dat korelace, která má vztah zprávy k instanci pracovního postupu.<br /><br /> Použití **inicializovat korelace** dialogové okno Konfigurace <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>. Další informace o použití toto dialogové okno, najdete v článku [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) článku.|

## <a name="see-also"></a>Viz také:

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)