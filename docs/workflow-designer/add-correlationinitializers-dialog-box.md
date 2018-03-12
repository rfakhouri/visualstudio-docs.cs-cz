---
title: "CorrelationInitializers dialogové okno Přidat | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a5e26e3335622d96c3757cb9caa004b1f3a99192
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="add-correlationinitializers-dialog-box"></a>CorrelationInitializers dialogové okno Přidat
**Přidat inicializátory korelace** dialogové okno v Návrháři pracovních postupů Windows slouží ke konfiguraci **CorrelationInitializers** vlastnosti <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Další informace o návrháře aktivit, které používají toto políčko, najdete v článku [odeslat](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), a [SendAndReceiveReply ](../workflow-designer/sendandreceivereply-template-designer.md) témata.

 Inicializátory korelace v kolekci zadaným tohoto dialogového okna můžete inicializovat založených na dotazech kontextu, zpětného volání kontextu nebo požadavku a odpovědi korelací mezi aktivitami zasílání zpráv.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **přidat inicializátory korelace** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Přidat inicializátoru**|Klikněte na tlačítko **přidat inicializovat** políčko k přidání dalších inicializátoru do kolekce.|
|**Typ korelace**|Určuje typ inicializátoru korelace. Existují čtyři typy:<br /><br /> 1.  Korelace inicializátoru zpětného volání k určení <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.<br />2.  Korelace inicializátoru kontext k určení <xref:System.ServiceModel.Activities.CorrelationInitializer>.<br />3.  Inicializátoru korelace požadavku a odpovědi k určení <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.<br />4.  Korelace inicializátoru dotazu zadat <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.<br /><br /> Chcete-li upravit **CorrelationType**<br /><br /> 1.  Karta na konkrétní řádek v **přidat inicializátoru** DataGrid.<br />2.  Stisknutím kláves Ctrl + Tab k nastavení fokusu **CorrelationTypeComboBox**<br />3.  Stiskněte klávesu Alt + Šipka dolů objevil **ComboBox** a upravit ho.|
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy použitou k extrakci korelace data z příchozí a odchozí zprávy. Tento seznam je platný pouze při použití <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> typy.|

## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>Chcete-li spustit dialogové okno Přidat inicializátory korelace
 **Přidat inicializátory korelace** dialogové okno používá **odeslat**, **Receive**, **ReceiveAndSendReply**, a  **SendAndReceiveReply** Designer. K nim přistupovat je podobný v každém případě a případu, který zahrnuje **Receive** Návrhář znázorňují postup je tady použijte.

 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **CorrelationInitializers** v mřížce vlastnost pro vlastnost **přidat Inicializátory korelace** dialogové okno se objeví.

## <a name="see-also"></a>Viz také

- [Korelace dialogové okno Přidat](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)