---
title: Návrhář postupu provádění - CorrelationInitializers dialogové okno Přidat
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d54724655db7147c06687aa88a4fe623bb277a45
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756937"
---
# <a name="add-correlationinitializers-dialog-box"></a>Dialogové okno Přidat inicializátory korelace

**Přidat inicializátory korelace** dialogové okno v Návrháři pracovních postupů slouží ke konfiguraci **CorrelationInitializers** vlastnosti <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Další informace o návrháře aktivit, které používají toto políčko, najdete v článku [odeslat](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), a [SendAndReceiveReply ](../workflow-designer/sendandreceivereply-template-designer.md) témata.

Inicializátory korelace v kolekci zadaným tohoto dialogového okna můžete inicializovat následující korelací mezi aktivitami zasílání zpráv:

- na základě dotazů
- kontext
- zpětné volání kontextu
- požadavek odpověď

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **přidat inicializátory korelace** dialogové okno:

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Přidat inicializátoru**|Klikněte na tlačítko **přidat inicializovat** políčko k přidání dalších inicializátoru do kolekce.|
|**Typ korelace**|Určuje typ inicializátoru korelace. Existují čtyři typy:<br /><br /> 1. Korelace inicializátoru zpětného volání k určení <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.<br />2. Korelace inicializátoru kontext k určení <xref:System.ServiceModel.Activities.CorrelationInitializer>.<br />3. Inicializátoru korelace požadavku a odpovědi k určení <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.<br />4. Korelace inicializátoru dotazu zadat <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.<br /><br /> Chcete-li upravit **CorrelationType**<br /><br /> 1. Karta na konkrétní řádek v **přidat inicializátoru** DataGrid.<br />2. K nastavení fokusu **CorrelationTypeComboBox**, stiskněte klávesu **Ctrl**+**kartě**.<br />3. Stiskněte klávesu Alt + Šipka dolů objevil **ComboBox** a upravit ho.|
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy použitou k extrakci korelace data z příchozí a odchozí zprávy. Tento seznam je platný pouze při použití <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> typy.|

## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>Chcete-li spustit dialogové okno Přidat inicializátory korelace

 **Přidat inicializátory korelace** dialogové okno používá **odeslat**, **Receive**, **ReceiveAndSendReply**, a  **SendAndReceiveReply** Designer. K nim přistupovat je podobný v každém případě a případu, který zahrnuje **Receive** Návrhář zde slouží k znázorňují postup.

 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů, kde jsou umístěny aktivity. Vyřazení **Receive** vytvoří Návrhář aktivity <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **CorrelationInitializers** v mřížce vlastnost pro vlastnost **přidat Inicializátory korelace** dialogové okno se objeví.

## <a name="see-also"></a>Viz také:

- [Korelace dialogové okno Přidat](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)