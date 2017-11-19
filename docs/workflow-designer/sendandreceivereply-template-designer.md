---
title: "Návrhář šablony SendAndReceiveReply | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.SendAndReceiveReply.UI
- System.ServiceModel.Activities.ReceiveReply.UI
ms.assetid: 818a8c84-6593-416d-b016-1d91b85ffb68
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: be208d526fdc9f1d6f434425e3931b0f0a6510f5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="sendandreceivereply-template-designer"></a>Návrhář šablony SendAndReceiveReply
**SendAndReceiveReply** šablona se používá k vytvoření pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity, která jsou korelační jako součást systému exchange zprávu žádosti a odpovědi vzor na straně klienta.  
  
## <a name="the-sendandreceivereply-template"></a>Šablona SendAndReceiveReply  
 Přidání **SendAndReceiveReply** šablona nemá tři věci kromě vytvoření <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity:  
  
1.  Nakonfiguruje <xref:System.ServiceModel.Activities.Send.OperationName%2A>, <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> vlastnosti <xref:System.ServiceModel.Activities.Send> aktivity.  
  
2.  Váže <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> vlastnost <xref:System.ServiceModel.Activities.ReceiveReply> aktivitu <xref:System.ServiceModel.Activities.Send> aktivity.  
  
3.  Vytvoří <xref:System.ServiceModel.Activities.CorrelationHandle> jako proměnné v nadřazené aktivity.  
  
### <a name="using-the-sendandreceivereply-template-designer"></a>Pomocí návrháře šablony SendAndReceiveReply  
 **SendAndReceiveReply** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **SendAndReceiveReply** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Send> aktivity, která se dá nakonfigurovat s **odeslat** Návrhář aktivity a korelační <xref:System.ServiceModel.Activities.ReceiveReply> , se dá nakonfigurovat s **ReceiveReplyForSend** designer.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]pomocí **odeslat** návrháře konfigurace <xref:System.ServiceModel.Activities.Send> aktivity, najdete v části [odeslat](../workflow-designer/send-activity-designer.md) tématu.  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]pomocí **ReceiveReplyForSend** návrháře konfigurace <xref:System.ServiceModel.Activities.ReceiveReply> aktivity, najdete v následující části.  
  
### <a name="properties-of-receivereply"></a>Vlastnosti ReceiveReply  
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.ReceiveReply> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v mřížce vlastnosti a lze upravit některé na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]plochu návrháře.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Výchozí hodnota je ReceiveReplyForSend.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít tuto hodnotu.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>|Hodnota TRUE|Odkaz na <xref:System.ServiceModel.Activities.Send> aktivity spárovat s tímto <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Tato vlastnost nesmí být **null**. <xref:System.ServiceModel.Activities.Send>a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity se používají společně na straně klienta pro model vzorcem zasílání zpráv požadavků a odpovědí. Tato vlastnost určuje, které <xref:System.ServiceModel.Activities.Send> aktivity je spárován. V návrháři, nelze upravovat tuto vlastnost, protože je automaticky vázána na <xref:System.ServiceModel.Activities.Send> aktivity, ze kterého jste vytvořili <xref:System.ServiceModel.Activities.ReceiveReply> aktivity.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Content%2A>|False|Určuje obsah zprávy nebo parametr přijímat. Může být buď <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Upravit tuto vlastnost tak, že kliknete na tlačítko se třemi tečkami vedle položky **obsahu** pole nebo vlastnost mřížky kliknutím na **definovat...**  tlačítko vedle položky **obsahu** v popisek **Receive** aktivity plochu návrháře. Obě zobrazení **obsahu definice** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto políčka naleznete v tématu [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.CorrelationInitializers%2A>|False|Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objekty, které inicializovat více <xref:System.ServiceModel.Activities.CorrelationHandle> objekty, které tato konfigurace <xref:System.ServiceModel.Activities.Receive> aktivita v rámci pracovního postupu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> vlastnost v mřížce vlastnosti otevřete **přidat inicializátory korelace** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto políčka, najdete v tématu [dialogové okno Přidat CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.ReceiveReply.Action%2A>|False|Určuje akci záhlaví zprávy. Pokud není explicitně nastavena, jeho výchozí hodnota:<br /><br /> **https://tempuri.org/ {obor názvů kontraktu služby} / {název kontraktu služby} / {operaci name}.**|  
  
## <a name="see-also"></a>Viz také  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Přijímat](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Odeslat](../workflow-designer/send-activity-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)