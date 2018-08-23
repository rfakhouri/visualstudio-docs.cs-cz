---
title: Návrháři aktivit zasílání zpráv | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 897e63cf-a42f-4edd-876f-c4ccfffaf6d6
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 6c592c748775361f3ed6a746accd0aa30dcc42af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671097"
---
# <a name="messaging-activity-designers"></a>Návrháři aktivit zasílání zpráv
Zasílání zpráv návrháři aktivit umožňují vytvářet a konfigurovat zasílání zpráv aktivity, které odesílat a přijímat [!INCLUDE[indigo1](../includes/indigo1-md.md)] zprávy v rámci [!INCLUDE[wf](../includes/wf-md.md)] aplikace. [!INCLUDE[netfx40_long](../includes/netfx40-long-md.md)] Představuje pět zasílání zpráv aktivity a [!INCLUDE[wfd1](../includes/wfd1-md.md)] poskytuje dva nové návrháře šablony, které vám umožní spravovat zasílání zpráv v rámci pracovního postupu. V tématech obsažené v této části a uvedené v následující tabulce najdete pokyny, jak používat [!INCLUDE[wfd2](../includes/wfd2-md.md)] návrhářů aktivit a šablony.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Aktivita zpráva|Popis|  
|----------------------|-----------------|  
|[CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.CorrelationScope> aktivitu, která poskytuje implicitní správu podřízené aktivity s zasílání zpráv <xref:System.ServiceModel.Activities.CorrelationHandle> objektu.|  
|[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivitu, která slouží k inicializaci korelace bez odesílání nebo přijímání zprávy.|  
|[Zobrazit](../workflow-designer/receive-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.Receive> aktivitu, která přijímá zprávy ze služby.|  
|[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)|Vytvoří pár předem nakonfigurované <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity.|  
|[Odeslat](../workflow-designer/send-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.Send> aktivitu, která odešle zprávu do služby.|  
|[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)|Vytvoří pár předem nakonfigurované <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity.|  
|[TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivitu, která umožňuje tok transakcí do pracovního postupu.|  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Activities.Activity>  
  
 <xref:System.ServiceModel.Activities.CorrelationScope>  
  
 <xref:System.ServiceModel.Activities.Receive>  
  
 <xref:System.ServiceModel.Activities.Send>  
  
 <xref:System.ServiceModel.Activities.ReceiveReply>  
  
 <xref:System.ServiceModel.Activities.SendReply>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
## <a name="related-sections"></a>Související oddíly  
 U jiných typů návrháři aktivit naleznete v následujících tématech.  
  
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)  
  
 [Používání návrhářů aktivit](../workflow-designer/using-the-activity-designers.md)  
  
 [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)  
  
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)  
  
 [Primitivní elementy](../workflow-designer/primitives-activity-designers.md)  
  
 [Transakce](../workflow-designer/transaction-activity-designers.md)  
  
 [Kolekce](../workflow-designer/collection-activity-designers.md)  
  
 [Zpracování chyb](../workflow-designer/error-handling-activity-designers.md)  
  
## <a name="external-resources"></a>Externí zdroje  
 [Používání návrhářů aktivit](../workflow-designer/using-the-activity-designers.md)