---
title: Návrhář postupu provádění – přidat inicializátory korelace dialogové okno
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21c030295d325ea1ee4d546356f8cda5ef6ffd3f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946648"
---
# <a name="add-correlationinitializers-dialog-box"></a>Dialogové okno Přidat inicializátory korelace

**Přidat inicializátory korelace** dialogové okno se používá v Návrháři pracovních postupů ke konfiguraci **correlationinitializers uveden** vlastnosti <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Další informace o návrháři aktivit, které používají toto políčko, najdete v článku [odeslat](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), a [SendAndReceiveReply ](../workflow-designer/sendandreceivereply-template-designer.md) témata.

Inicializátory korelace v kolekci specifikované se toto dialogové okno můžete inicializovat následující korelace mezi zasílání zpráv aktivity:

- založené na dotazech
- kontext
- kontext zpětného volání
- požadavek odpověď

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **přidat inicializátory korelace** dialogové okno:

|Prvek uživatelského rozhraní (UI)|Popis|
|-|-----------------|
|**Přidat inicializátor**|Klikněte na tlačítko **přidat inicializační** políčko k přidání dalších inicializátor kolekce.|
|**Typ korelace**|Určuje typ korelace. Existují čtyři typy lze vybírat:<br /><br /> 1. Korelace inicializátoru zpětného volání k určení <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.<br />2. Korelace inicializátoru kontext k určení <xref:System.ServiceModel.Activities.CorrelationInitializer>.<br />3. Inicializátoru korelace požadavku a odpovědi k určení <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.<br />4. Inicializátor korelace dotazu k určení <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.<br /><br /> Chcete-li upravit **CorrelationType**<br /><br /> 1. Karty na konkrétní řádek v **přidat inicializátor** ovládacího prvku DataGrid.<br />2. K nastavení fokusu **CorrelationTypeComboBox**, stiskněte klávesu **Ctrl**+**kartu**.<br />3. Stisknutím klávesy Alt + Šipka dolů objevil **– pole se seznamem** a upravit ho.|
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy používané k extrakci korelace dat z příchozí a odchozí zprávy. Tento seznam je platný pouze při použití <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> typy.|

## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>Chcete-li spustit dialogové okno Přidat inicializátory korelace

 **Přidat inicializátory korelace** dialogové okno používá **odeslat**, **Receive**, **ReceiveAndSendReply**, a  **SendAndReceiveReply** návrháře. Přístup k nim je podobné jako v každém případě a případ, který zahrnuje **Receive** návrháře se zde používá k znázorňují postup.

 **Receive** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou umístěny. Vyřazení **Receive** vytvoří Návrhář aktivity <xref:System.ServiceModel.Activities.Receive> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** návrháře aktivit a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **correlationinitializers uveden** v mřížce vlastností pro vlastnost **přidat Inicializátory korelace** dialogového okna.

## <a name="see-also"></a>Viz také:

- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)