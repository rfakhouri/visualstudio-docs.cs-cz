---
title: "Zasílání zpráv návrháře aktivit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 897e63cf-a42f-4edd-876f-c4ccfffaf6d6
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 481d9e577989b1bd75cea22e0faab6d8a1cc64cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="messaging-activity-designers"></a>Zasílání zpráv návrháře aktivit
Zasílání zpráv návrháře aktivit, které se používají k vytvoření a konfigurace zasílání zpráv aktivity, které odesílat a přijímat [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] zprávy z uvnitř [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace. [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] Zavádí pět aktivity zasílání zpráv a [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] poskytuje dva nové návrháři šablon, které vám umožní spravovat zasílání zpráv v pracovním postupu. V tématech obsažené v této části a uvedené v následující tabulce najdete pokyny k použití [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Designer aktivity a šablony.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Činnost zpráv|Popis|  
|----------------------|-----------------|  
|[CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)|Vytváří a konfiguruje <xref:System.ServiceModel.Activities.CorrelationScope> aktivity, která nabízí implicitní správu podřízené aktivity s zasílání zpráv <xref:System.ServiceModel.Activities.CorrelationHandle> objektu.|  
|[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)|Vytvoří a nakonfiguruje <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity, která se používá k chybě při inicializaci korelace bez odesílání nebo přijímání zprávy.|  
|[Přijímat](../workflow-designer/receive-activity-designer.md)|Vytváří a konfiguruje <xref:System.ServiceModel.Activities.Receive> aktivity, která přijímá zprávy od služby.|  
|[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)|Vytvoří pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity.|  
|[Odeslat](../workflow-designer/send-activity-designer.md)|Vytváří a konfiguruje <xref:System.ServiceModel.Activities.Send> aktivity, která odešle zprávu do služby.|  
|[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)|Vytvoří pár předem nakonfigurovaná <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity v rámci <xref:System.Activities.Statements.Sequence> aktivity.|  
|[TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)|Vytváří a konfiguruje <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity, která umožňuje tok transakcí do pracovního postupu.|  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Activities.Activity>  
  
 <xref:System.ServiceModel.Activities.CorrelationScope>  
  
 <xref:System.ServiceModel.Activities.Receive>  
  
 <xref:System.ServiceModel.Activities.Send>  
  
 <xref:System.ServiceModel.Activities.ReceiveReply>  
  
 <xref:System.ServiceModel.Activities.SendReply>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
## <a name="related-sections"></a>Související oddíly  
 U jiných typů návrháře aktivit najdete v následujících tématech.  
  
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