---
title: Návrhář aktivity Cancellationscope | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: f8ddd5472a0e6540f8593c20e7f7d5735384f8e6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629866"
---
# <a name="cancellationscope-activity-designer"></a>Návrhář aktivity CancellationScope
**CancellationScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CancellationScope> aktivity.  
  
## <a name="the-cancellationscope-activity"></a>Aktivity CancellationScope  
 <xref:System.Activities.Statements.CancellationScope> Aktivit vám umožní určit aktivitu pro spouštění a rušení logiku pro danou aktivitu.  
  
### <a name="using-the-cancellationscope-activity-designer"></a>Pomocí aktivity Cancellationscope  
 **CancellationScope** návrháře aktivit najdete v **transakce** kategorii **nástrojů**, který přistupuje po kliknutí **sady nástrojů**  karty [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **CancellationScope** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.CancellationScope> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z CancellationScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **CancellationScope** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností.  
  
### <a name="the-cancellationscope-properties"></a>Vlastnosti CancellationScope  
 Následující tabulka ukazuje <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastností, ale další vlastnosti nutné upravit na [!INCLUDE[wfd2](../includes/wfd2-md.md)] povrchu.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je CancellationScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Hodnota TRUE|Určuje aktivity, pro které zrušení logiky poskytnuty. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.Body%2A> aktivity, rozevírací aktivitu z **nástrojů** do **text** pole na **CancellationScope** Návrhář aktivity s text nápovědy "rozevírací Aktivity sem".|  
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Hodnota TRUE|Určuje, která se spustí v případě zrušení aktivity. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> aktivity, rozevírací aktivitu z **nástrojů** do **CancellationHandler** pole na **CancellationScope** Návrhář aktivity s nápovědou text "Aktivity Sem přetáhněte".|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [Aktivita CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Kompenzace](../workflow-designer/compensate-activity-designer.md)   
 [potvrzení](../workflow-designer/confirm-activity-designer.md)   
 [Objekt TransactionScope](../workflow-designer/transactionscope-activity-designer.md)