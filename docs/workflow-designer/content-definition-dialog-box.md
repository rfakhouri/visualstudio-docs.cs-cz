---
title: "Dialogové okno Definice obsahu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: "3"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: c87180f1f1c0b2c578977021b6a9511e629d10bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="content-definition-dialog-box"></a>Dialogové okno Definice obsahu
**Obsahu definice** dialogové okno se používá v [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] nakonfigurovat **obsahu** vlastnosti <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. [!INCLUDE[crabout](../test/includes/crabout_md.md)]návrháře aktivit, které používají toto políčko, najdete v článku [odeslat](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), a [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) témata.  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializovat korelace** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Zpráva**|Určuje zprávu, která obsah s **zprávy data** výraz textového pole a zadejte pomocí **typ zprávy** rozevíracího seznamu. Ve výchozím nastavení **obsahu definice** používá <xref:System.ServiceModel.Activities.ReceiveMessageContent>, která očekává <xref:System.ServiceModel.Channels.Message> nebo zprávu smlouvy type v rámci služby definice pracovního postupu.|  
|**Parametry**|Klikněte **parametry** přepínač použít <xref:System.ServiceModel.Activities.ReceiveParametersContent>, která očekává kontraktu dat. Použít mřížku dat nastavit obecné kolekce <xref:System.Activities.OutArgument> jejichž hodnoty jsou přiřazeny k proměnné parametry v aktuálním pracovním postupu dvojice klíč/hodnota.|  
  
 **Obsahu definice** dialogové okno používá **odeslat**, **Receive**, **ReceiveAndSendReply**, a  **SendAndReceiveReply** Designer. K nim přistupovat je podobný v každém případě a Receive případě zde slouží k znázorňují postup.  
  
 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu u (obsah) **obsahu** vlastnost mřížku vlastností pro **obsahu definice**dialogové okno se objeví.  
  
 Obsah lze zadat v rámci **zpráva** část <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo uvnitř **parametr** část <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity.  
  
## <a name="see-also"></a>Viz také  
 [Nápověda k uživatelskému rozhraní návrháře postupu provádění](../workflow-designer/workflow-designer-ui-help.md)