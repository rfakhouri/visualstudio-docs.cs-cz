---
title: Návrhář postupu provádění – Návrhář aktivity odesílání
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4dfadf0e11104867461ee3fe2374301a3438fdd4
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117735"
---
# <a name="send-activity-designer"></a>Návrhář aktivity Send

**Odeslat** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.Send> aktivity.

## <a name="the-send-activity"></a>Aktivita odeslání

 A <xref:System.ServiceModel.Activities.Send> aktivita se používá k odeslání zprávy do služby. A <xref:System.ServiceModel.Activities.ReceiveReply> aktivity mohou být vázány na <xref:System.ServiceModel.Activities.Send> aktivity, která přijímá zprávy jako součást vzorce výměny zpráv požadavků a odpovědí na straně klienta.

### <a name="using-the-send-activity-designer"></a>Pomocí návrháře aktivity odesílání

Přístup **odeslat** Návrhář aktivity v **zasílání zpráv** kategorii **sada nástrojů**. **Odeslat** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Send> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> o odeslání. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **odeslat** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

K vytvoření <xref:System.ServiceModel.Activities.ReceiveReply> aktivity a navázat jej na vybrané <xref:System.ServiceModel.Activities.Send> aktivity, klikněte pravým tlačítkem myši **odeslat** návrháře, klikněte na aktivitu **vytvořit ReceiveReply** položka v místní nabídce a **ReceiveReplyForSend** designer se zobrazí pod **odeslat** designer. <xref:System.ServiceModel.Activities.ReceiveReply> Aktivity je aktivitou, která přijme zprávu o jako součást vzorce výměny zpráv požadavků a odpovědí na straně klienta. Můžete nakonfigurovat pomocí **ReceiveReplyForSend** designer.

Případně **SendAndReceiveReply** návrhář šablony v **zasílání zpráv** kategorii **sada nástrojů** lze vytvořit pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Send>a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Další informace o použití **SendAndReceiveReply** a **ReceiveReplyForSend** šablony, najdete v článku [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) tématu.

### <a name="the-send-activity-properties"></a>Vlastnosti aktivity odesílání

Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.Send> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnosti nebo na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.ServiceModel.Activities.Send> aktivity. Výchozí hodnota je odeslat. I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.ServiceModel.Activities.Send.OperationName%2A>|Hodnota TRUE|Název operace služby volat to <xref:System.ServiceModel.Activities.Send> aktivity. Tato vlastnost se používá pro konstrukci výchozí hodnota **akce** vlastnost Pokud **akce** není explicitně nastavena vlastnost.|
|<xref:System.ServiceModel.Activities.Send.ServiceContractName%2A>|Hodnota TRUE|Název kontraktu služby, který implementuje službu, která se má volat.|
|<xref:System.ServiceModel.Activities.Send.Content%2A>|False|Určuje obsah zprávy nebo parametr přijímat. Může být buď <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity. Upravit tuto vlastnost tak, že vyberete se třemi tečkami vedle položky **obsahu** pole nebo vlastnost mřížky kliknutím na **definovat...**  tlačítko vedle položky **obsahu** v popisek **Receive** aktivity plochu návrháře. Obě zobrazení **obsahu definice** dialogové okno. Další informace o tom, jak pomocí tohoto políčka, najdete v článku [dialogové okno obsahu definice](../workflow-designer/content-definition-dialog-box.md) tématu.|
|<xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>|False|Určuje, <xref:System.ServiceModel.Activities.CorrelationHandle> umožňuje směrovat zprávy do instance příslušné pracovního postupu.<br /><br /> Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> vlastnost v mřížce vlastnosti otevřete **Editor výrazů** dialogové okno. Další informace o použití tohoto dialogového okna najdete v tématu [postupy: použití editoru výraz](../workflow-designer/how-to-use-the-expression-editor.md) tématu.|
|<xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>|False|Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objekty, které inicializovat více <xref:System.ServiceModel.Activities.CorrelationHandle> objekty, které tato konfigurace <xref:System.ServiceModel.Activities.Send> aktivita v rámci pracovního postupu. Klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> vlastnost v mřížce vlastnosti otevřete **přidat inicializátory korelace** dialogové okno. Další informace o použití tohoto políčka, najdete v článku [dialogové okno Přidat CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) tématu.|
|<xref:System.ServiceModel.Activities.Send.KnownTypes%2A>|False|Kolekce známé typy pro operace služby, která se má volat tento <xref:System.ServiceModel.Activities.Send> aktivity. Tato vlastnost by měla používá ve spojení s <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> vlastnost nastavena na hodnotu <xref:System.Runtime.Serialization.DataContractSerializer>. Je ignorována, pokud <xref:System.Xml.Serialization.XmlSerializer> se používá.<br /><br /> Vyberte tlačítko se třemi tečkami vedle položky **KnownTypes** pole v mřížce vlastnosti se zobrazí **Editor kolekce typ** dialogové okno, pomocí kterého můžete přidat příslušných typů.<br /><br /> Vyberte tlačítko se třemi tečkami vedle položky **KnownTypes** pole v mřížce vlastnosti se zobrazí **Editor kolekce typ** dialogové, pomocí kterého můžete přidat relevantní typy. Další informace o použití tohoto políčka, najdete v článku [dialogové okno Editor kolekcí typu](../workflow-designer/type-collection-editor-dialog-box.md) tématu.|
|<xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A>|Hodnota TRUE|Určuje, <xref:System.Net.Security.ProtectionLevel> pro zprávu.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> znamená jenom ověřování.<br />2. <xref:System.Net.Security.ProtectionLevel> znamená podepisování dat. k zajištění integrity dat přenášených.<br />3. <xref:System.Net.Security.ProtectionLevel> znamená šifrování a podepisování dat k zajištění důvěrnosti a integrity dat přenášených.|
|<xref:System.ServiceModel.Activities.Send.SerializerOption%2A>|Hodnota TRUE|Serializátoru, který chcete použít pro operaci služby má být volána <xref:System.ServiceModel.Activities.Send> aktivity. Výchozí hodnota je <xref:System.Runtime.Serialization.DataContractSerializer>, který serializuje a deserializuje instance typu do datového proudu XML nebo dokumentu s použitím kontraktu zadaná data.|
|<xref:System.ServiceModel.Activities.Send.Action%2A>|False|Určuje akci záhlaví zprávy. Pokud není explicitně nastavena, jeho výchozí hodnota je: https://tempuri.org/{service smlouvy obor názvů} / {název kontraktu služby} / {operaci name}. Pokud zadaný na <xref:System.ServiceModel.Activities.Send> aktivity, <xref:System.ServiceModel.Activities.Receive> aktivity, která přijímá zprávy musí mít stejnou hodnotu pro zpráva, která má být správně doručena.|
|<xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A>||<xref:System.Security.Principal.TokenImpersonationLevel> Povolené pro příjemce zprávy. Definuje zosobnění úrovně zabezpečení, kterými se na úroveň, ke kterému může proces serveru fungovat jménem procesu klienta.<xref:System.Security.Principal.TokenImpersonationLevel> Označuje, že není přiřazen úroveň zosobnění. <xref:System.Security.Principal.TokenImpersonationLevel> Označuje, že proces serveru nelze získat identifikační informace o klientovi a nelze jej zosobnit klienta. <xref:System.Security.Principal.TokenImpersonationLevel> Označuje, že proces serveru můžete získat informace o klientovi, jako je například identifikátory zabezpečení a oprávnění, ale že nelze zosobnit klienta. To je užitečné pro servery, které exportovat vlastní objekty, například databáze produkty, které export tabulek a zobrazení. Pomocí informací o načtené zabezpečení klienta, serveru můžete rozhodnout ověření přístupu k aniž by bylo možné používat další služby, které používají klienta kontext zabezpečení. <xref:System.Security.Principal.TokenImpersonationLevel> Označuje, že proces serveru může zosobnit kontext zabezpečení klienta ve svém místním systému. Server nelze zosobnit klienta na vzdálené systémy. <xref:System.Security.Principal.TokenImpersonationLevel> Označuje, že proces serveru může zosobnit kontext zabezpečení klienta na vzdálené systémy.|
|<xref:System.ServiceModel.Activities.Send.Endpoint%2A>||<xref:System.ServiceModel.Endpoint> , <xref:System.ServiceModel.Activities.Send> Aktivita odesílá zprávy do. Pokud je tato vlastnost nastavená <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> vlastnost by měla být **null**.|
|<xref:System.ServiceModel.Activities.Send.EndpointAddress%2A>||<xref:System.ServiceModel.EndpointAddress> Na které je zpráva odeslána.|
|<xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A>||Název konfigurace koncového bodu. Tato vlastnost nastavena, když konfigurujete koncový bod v konfiguračním souboru. Tato vlastnost by měla být nastavená na daný název  **\<endpoint >** element v konfiguračním souboru. Pokud je tato vlastnost nastavena, <xref:System.ServiceModel.Activities.Send.Endpoint%2A> vlastnost by měla být **null**.|

## <a name="see-also"></a>Viz také:

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)