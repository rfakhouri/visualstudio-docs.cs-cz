---
title: Návrhář aktivity TransactedReceiveScope | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f4864a19cf48b468abed90e120e4924237653cec
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976701"
---
# <a name="transactedreceivescope-activity-designer"></a>Návrhář aktivity TransactedReceiveScope
**TransactedReceiveScope** Návrhář slouží k vytvoření a konfigurace <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity.  
  
## <a name="the-transactedreceivescope-activity"></a>Aktivity TransactedReceiveScope  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivity umožňuje transakce do serveru transakce vytvořené pomocí pracovního postupu nebo dispečera.  
  
### <a name="using-the-transactedreceivescope-activity-designer"></a>Návrhář aktivity TransactedReceiveScope pomocí  
 **TransactedReceiveScope** návrháře aktivit najdete v **zasílání zpráv** kategorii **nástrojů**, který přistupuje po kliknutí **sady nástrojů**  kartě [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **TransactedReceiveScope** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity s výchozím **DisplayName** transactedreceivescope. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **TransactedReceiveScope** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
 **TransactedReceiveScope** Návrhář obsahuje **žádosti** a **tělo** polí. Ty se používají ke konfiguraci <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> vlastnost, která určuje <xref:System.ServiceModel.Activities.Receive> aktivity a <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> vlastnost, která určuje jiný <xref:System.Activities.Activity>. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> Vytvoří transakci. Potom transakce je k okolí rozsahu <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> tak, aby všechny aktivity v rámci tohoto oboru spustí v této transakci.  
  
### <a name="the-transactedreceivescope-properties"></a>Vlastnosti rozsahu TransactedReceiveScope  
 Následující tabulka ukazuje <xref:System.ServiceModel.Activities.TransactedReceiveScope> vlastnosti a popisuje, jak se používají v návrháři. Tyto <xref:System.Activities.Activity.DisplayName%2A> vlastnost lze upravit v mřížce vlastností nebo na [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface, ale ostatní musí upravit na návrhové ploše.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity. Výchozí hodnota je rozsahu TransactedReceiveScope.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> název není bezpodmínečně nutné, je osvědčeným postupem použít zobrazovaný název.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|Pravda|Drops <xref:System.ServiceModel.Activities.Receive> aktivitu **žádosti** bloku na plochu návrháře aktivit.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Drops <xref:System.Activities.Activity> do **tělo** bloku na plochu návrháře aktivit.|  
  
## <a name="see-also"></a>Viz také  
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [Zobrazit](../workflow-designer/receive-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [Odeslat](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)