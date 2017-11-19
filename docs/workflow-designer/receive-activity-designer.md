---
title: "Přijímat Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68d198675f5b0b91320e9c21d497caf225798cc7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="receive-activity-designer"></a>Přijímat Návrhář aktivity
**Receive** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.Receive> aktivity. A <xref:System.ServiceModel.Activities.Receive> aktivitu, která obdrží zprávu, která může být buď předdefinovaný typ, jako je aktivita <xref:System.ServiceModel.Channels.Message>, <xref:System.IO.Stream> nebo <xref:System.Xml.Linq.XElement>, nebo kontrakt dat definované aplikací, kontrakt zprávy nebo XML třídu, která může serializovat.  
  
## <a name="the-receive-activity"></a>Přijímat aktivity  
 <xref:System.ServiceModel.Activities.Receive> Aktivity může přijímat položku jeden nebo více položek v závislosti na typu přijmout obsah použít. A <xref:System.ServiceModel.Activities.SendReply> aktivity mohou být vázány na <xref:System.ServiceModel.Activities.Receive> aktivity, která přijímá zprávy jako součást vzorce výměny zpráv požadavků a odpovědí ve službě.  
  
### <a name="using-the-receive-activity-designer"></a>Pomocí přijímat Návrhář aktivity  
 **Receive** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **Receive** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
 K vytvoření <xref:System.ServiceModel.Activities.SendReply> aktivity a navázat jej na vybrané <xref:System.ServiceModel.Activities.Receive> aktivity, klikněte pravým tlačítkem myši **Receive** návrháře, klikněte na aktivitu **vytvořit SendReply** položka v místní nabídce a **SendReplyToReceive** designer se zobrazí pod **Receive** designer. <xref:System.ServiceModel.Activities.SendReply> Aktivity je aktivitou, která odešle zprávu odpovědi jako součást vzorce výměny zpráv požadavků a odpovědí ve službě. Můžete nakonfigurovat pomocí **SendReplyToReceive** designer.  
  
 Případně **ReceiveAndSendReply** návrhář šablony v **zasílání zpráv** kategorii **sada nástrojů** lze vytvořit pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Receive>a <xref:System.ServiceModel.Activities.SendReply> aktivity. [!INCLUDE[crabout](../test/includes/crabout_md.md)]použití **ReceiveAndSendReply** a **SendReplyToReceive** šablony, najdete v článku [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md) tématu.  
  
### <a name="the-receive-activity-properties"></a>Zobrazí vlastnosti aktivit  
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.Receive> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat vlastnosti mřížky nebo na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor. Je požadovaná vlastnost pouze <xref:System.ServiceModel.Activities.Receive.OperationName%2A> vlastnost.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.ServiceModel.Activities.Receive> aktivity. Výchozí hodnota je Receive.<br /><br /> I když používání jiné než výchozí hodnota popisný <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít tuto hodnotu.|  
|<xref:System.ServiceModel.Activities.Receive.OperationName%2A>|Hodnota TRUE|Určuje název služby operace implementované to <xref:System.ServiceModel.Activities.Receive> aktivity. Tato vlastnost se používá pro konstrukci výchozí hodnota **akce** vlastnost Pokud **akce** není explicitně nastavena vlastnost.|  
|<xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>|False|Určuje název kontraktu služby. Tato vlastnost slouží k operacím služby skupiny do kontrakty jednotlivých služeb. Všechny <xref:System.ServiceModel.Activities.Receive> aktivity, které mají stejnou <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> jsou seskupené do stejné kontrakt služby (WSDL Port typ). Výchozí hodnota je plně kvalifikovaný název CLR aktivity nejvyšší úrovně (uživatel root).|  
|<xref:System.ServiceModel.Activities.Receive.Content%2A>|False|Určuje obsah zprávy nebo parametr přijímat. Může být buď <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Upravit tuto vlastnost tak, že kliknete na tlačítko se třemi tečkami vedle položky **obsahu** pole nebo vlastnost mřížky kliknutím na **definovat...**  tlačítko vedle položky **obsahu** v popisek **Receive** aktivity plochu návrháře. Obě zobrazení **obsahu definice** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto políčka naleznete v tématu [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>|False|Určuje korelací mezi <xref:System.ServiceModel.Activities.Receive> aktivity v operací služby pracovního postupu s <xref:System.ServiceModel.MessageQuerySet> objektu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost v mřížce vlastnosti otevřete **CorrelatesOn definice** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto dialogového okna, najdete v článku [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>|False|Určuje, <xref:System.ServiceModel.Activities.CorrelationHandle> umožňuje směrovat zprávy do instance příslušné pracovního postupu.<br /><br /> Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> vlastnost v mřížce vlastnosti otevřete **Editor výrazů** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto dialogového okna, najdete v článku [postup: pomocí editoru výraz](../workflow-designer/how-to-use-the-expression-editor.md) tématu.|  
|<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>|False|Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objekty, které inicializovat více <xref:System.ServiceModel.Activities.CorrelationHandle> objekty, které tato konfigurace <xref:System.ServiceModel.Activities.Receive> aktivita v rámci pracovního postupu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> vlastnost v mřížce vlastnosti otevřete **přidat inicializátory korelace** dialogové okno. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto políčka, najdete v tématu [dialogové okno Přidat CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>|False|Určuje hodnotu, která určuje, jestli se má zpracovat zprávu, pokud zpráva neodpovídá existující instance pracovního postupu vytvořit novou instanci pracovního postupu. Pokud je hodnota nastavená **true**, je vytvořena nová instance pracovního postupu zpracovat zprávu, pokud zpráva není korelační s existující instancí pracovního postupu.|  
|<xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>|False|Určuje kolekci známé typy pro operace služby, které jsou implementované to <xref:System.ServiceModel.Activities.Receive> aktivity. Tato vlastnost by měla používá ve spojení s <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> vlastnost nastavena na hodnotu <xref:System.Runtime.Serialization.DataContractSerializer>. Je ignorována, pokud <xref:System.Xml.Serialization.XmlSerializer> se používá.<br /><br /> Klikněte na tlačítko se třemi tečkami vedle položky **KnownTypes** pole v mřížce vlastnosti se zobrazí **Editor kolekce typ** dialogové, pomocí kterého můžete přidat relevantní typy. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Pomocí tohoto políčka, najdete v tématu [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) tématu.|  
|<xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A>|False|Určuje, <xref:System.Net.Security.ProtectionLevel> pro zprávu.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> znamená jenom ověřování.<br />2. <xref:System.Net.Security.ProtectionLevel> znamená podepisování dat. k zajištění integrity dat přenášených.<br />3. <xref:System.Net.Security.ProtectionLevel> znamená šifrování a podepisování dat k zajištění důvěrnosti a integrity dat přenášených.|  
|<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>|False|Určuje typ serializátoru pro operace služby, které jsou implementované <xref:System.ServiceModel.Activities.Receive> aktivity. Výchozí hodnota je <xref:System.Runtime.Serialization.DataContractSerializer>, který serializuje a deserializuje instance typu do datového proudu XML nebo dokument, který používá zadaný datový kontrakt. <xref:System.Xml.Serialization.XmlSerializer> Lze také pokud přes XML je potřeba další řízení.|  
|<xref:System.ServiceModel.Activities.Receive.Action%2A>|False|Určuje akci záhlaví zprávy. Pokud není explicitně nastavena, jeho výchozí hodnota je: https://tempuri.org/ {obor názvů kontraktu služby} / {název kontraktu služby} / {operaci name}.|  
  
## <a name="see-also"></a>Viz také  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Odeslat](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)