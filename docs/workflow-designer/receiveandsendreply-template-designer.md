---
title: Návrhář šablony ReceiveAndSendReply | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.ReceiveAndSendReply.UI
- System.ServiceModel.Activities.SendReply.UI
ms.assetid: d1d9a058-df7e-48f5-a2e7-3caeeba7eaa6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81edeb04abacedb81ad52da17369759ba9f1f222
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="receiveandsendreply-template-designer"></a>Návrhář šablony ReceiveAndSendReply

**ReceiveAndSendReply** šablona se používá k vytvoření pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity, která jsou korelační jako součást systému exchange zprávu žádosti a odpovědi vzor na serveru.

## <a name="the-receiveandsendreply-template"></a>Šablona ReceiveAndSendReply
 Přidání **ReceiveAndSendReply** šablona nemá tři věci kromě vytvoření <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity s <xref:System.Activities.Statements.Sequence> aktivity:

1.  Nakonfiguruje <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> vlastnosti <xref:System.ServiceModel.Activities.Receive> aktivity.

2.  Váže <xref:System.ServiceModel.Activities.SendReply.Request%2A> vlastnost <xref:System.ServiceModel.Activities.Receive> aktivitu <xref:System.ServiceModel.Activities.Send> aktivity.

3.  Vytvoří <xref:System.ServiceModel.Activities.CorrelationHandle> jako proměnné v nadřazené aktivity.

### <a name="using-the-receiveandsendreply-template-designer"></a>Pomocí návrháře šablony ReceiveAndSendReply
 **ReceiveAndSendReply** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  kartě v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **ReceiveAndSendReply** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivity, která se dá nakonfigurovat s **odeslat** Návrhář aktivity a korelační <xref:System.ServiceModel.Activities.SendReply> který lze nakonfigurovat pomocí návrháře SendReplyToReceive.

 Další informace o používání **Receive** návrháře konfigurace <xref:System.ServiceModel.Activities.Receive> aktivity, najdete v článku [Receive](../workflow-designer/receive-activity-designer.md) tématu.

 Další informace o používání **SendReplyToReceive** návrháře konfigurace <xref:System.ServiceModel.Activities.SendReply> aktivity, najdete v následující části.

### <a name="properties-of-sendreply"></a>Vlastnosti SendReply
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.SendReply> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v mřížce vlastnosti a lze upravit některé na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.ServiceModel.Activities.SendReply> aktivity. Výchozí hodnota je SendReplyToReceive.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít tuto hodnotu.|
|<xref:System.ServiceModel.Activities.SendReply.Request%2A>|Hodnota TRUE|Odkaz na <xref:System.ServiceModel.Activities.Receive> aktivity spárovat s tímto <xref:System.ServiceModel.Activities.SendReply> aktivity. Tato vlastnost nesmí být **null**. <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity se používají společně na serveru pro model vzorcem zasílání zpráv požadavků a odpovědí. Tato vlastnost určuje, které <xref:System.ServiceModel.Activities.Send> aktivity je spárován. V návrháři, nelze upravovat tuto vlastnost, protože je automaticky vázána na <xref:System.ServiceModel.Activities.Send> aktivity, ze kterého jste vytvořili <xref:System.ServiceModel.Activities.SendReply> aktivity.|
|<xref:System.ServiceModel.Activities.SendReply.Content%2A>|False|Určuje obsah zprávy nebo parametr přijímat. Může být buď <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Upravit tuto vlastnost tak, že kliknete na tlačítko se třemi tečkami vedle položky **obsahu** pole nebo vlastnost mřížky kliknutím na **definovat...**  tlačítko vedle položky **obsahu** v popisek **Receive** aktivity plochu návrháře. Obě zobrazení **obsahu definice** dialogové okno. Další informace o tom, jak pomocí tohoto políčka, najdete v článku [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md) tématu.|
|<xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A>|False|Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objekty, které inicializovat více <xref:System.ServiceModel.Activities.CorrelationHandle> objekty, které tato konfigurace <xref:System.ServiceModel.Activities.Receive> aktivita v rámci pracovního postupu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.SendReply.CorrelationInitializers%2A> vlastnost v mřížce vlastnosti otevřete **přidat inicializátory korelace** dialogové okno. Další informace o použití tohoto políčka, najdete v článku [dialogové okno Přidat CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) tématu.|
|<xref:System.ServiceModel.Activities.SendReply.Action%2A>|False|Určuje akci záhlaví zprávy. Pokud není explicitně nastavena, jeho výchozí hodnota:<br /><br /> **https://tempuri.org/{service Sbalit obor názvů} / {název kontraktu služby} / {název operace}**|
|<xref:System.ServiceModel.Activities.SendReply.PersistBeforeSend%2A>|False|Určuje, zda instance pracovního postupu by měl nastavit jako trvalý, předtím, než odešle zprávu s odpovědí. Výchozí hodnota je **false**.|

## <a name="see-also"></a>Viz také

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)