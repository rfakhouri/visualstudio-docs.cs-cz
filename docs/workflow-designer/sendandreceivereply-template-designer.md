---
title: Návrhář postupu provádění - SendAndReceiveReply Template Designer
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 282ba94c026b885cb6f8250b33beb98616376e8d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755808"
---
# <a name="sendandreceivereply-template-designer"></a>Návrhář šablony SendAndReceiveReply

**SendAndReceiveReply** šablona se používá k vytvoření pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Aktivity jsou součástí <xref:System.Activities.Statements.Sequence> aktivity a jsou korelační jako součást vzorce výměny zpráv požadavků a odpovědí na straně klienta.

## <a name="the-sendandreceivereply-template"></a>Šablona SendAndReceiveReply

Přidávání **SendAndReceiveReply** šablona nemá tři věci kromě vytvoření <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity:

- Nakonfiguruje <xref:System.ServiceModel.Activities.Send.OperationName%2A> a <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> vlastnosti <xref:System.ServiceModel.Activities.Send> aktivity.

- Váže <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> vlastnost <xref:System.ServiceModel.Activities.ReceiveReply> aktivitu <xref:System.ServiceModel.Activities.Send> aktivity.

- Vytvoří <xref:System.ServiceModel.Activities.CorrelationHandle> jako proměnné v nadřazené aktivity.

### <a name="use-the-sendandreceivereply-template-designer"></a>Pomocí nástroje SendAndReceiveReply Template Designer

Přístup **SendAndReceiveReply** Návrhář aktivity v **zasílání zpráv** kategorii **sada nástrojů**. **SendAndReceiveReply** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny. Vyřazení Návrhář aktivity vytvoří <xref:System.ServiceModel.Activities.Send> aktivity, která se dá nakonfigurovat s **odeslat** Návrhář aktivity a korelační <xref:System.ServiceModel.Activities.ReceiveReply> , se dá nakonfigurovat s **ReceiveReplyForSend** designer.

Další informace o používání **odeslat** návrháře konfigurace <xref:System.ServiceModel.Activities.Send> aktivity, najdete v části [odeslat](../workflow-designer/send-activity-designer.md).

### <a name="properties-of-receivereply"></a>Vlastnosti ReceiveReply

Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.ReceiveReply> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravovat v mřížce vlastnosti, a můžete upravit některé na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Výchozí hodnota je ReceiveReplyForSend.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je nejvhodnější použít tuto hodnotu.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|Hodnota TRUE|Odkaz na <xref:System.ServiceModel.Activities.Send> aktivity spárovat s tímto <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Tato vlastnost nesmí být **null**. <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity se používají společně na straně klienta pro model vzorcem zasílání zpráv požadavků a odpovědí. Tato vlastnost určuje, které <xref:System.ServiceModel.Activities.Send> aktivity je spárován. V návrháři, nelze upravovat tuto vlastnost, protože je automaticky vázána na <xref:System.ServiceModel.Activities.Send> aktivity, ze kterého jste vytvořili <xref:System.ServiceModel.Activities.ReceiveReply> aktivity.|
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|Určuje obsah zprávy nebo parametr přijímat. Může být buď <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Upravit tuto vlastnost tak, že kliknete na tlačítko se třemi tečkami vedle **obsahu** pole v tabulce vlastností, nebo kliknutím **definovat** vedle položky **obsahu** popisku na **Receive** aktivity plochu návrháře. Obě zobrazení **obsahu definice** dialogové okno. Další informace o tom, jak pomocí tohoto políčka najdete v tématu [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md).|
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objekty, které inicializovat více <xref:System.ServiceModel.Activities.CorrelationHandle> objekty, které tato konfigurace <xref:System.ServiceModel.Activities.Receive> aktivita v rámci pracovního postupu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> vlastnost v mřížce vlastnosti otevřete **přidat inicializátory korelace** dialogové okno. Další informace o použití tohoto políčka, najdete v části [dialogové okno Přidat CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md).|
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|Určuje akci záhlaví zprávy. Pokud je nastavené není explicitně, jeho výchozí hodnota:<br /><br /> **https://tempuri.org/{service Sbalit obor názvů} / {název kontraktu služby} / {operaci name}.**|

## <a name="see-also"></a>Viz také:

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)