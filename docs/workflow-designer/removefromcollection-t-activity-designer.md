---
title: "RemoveFromCollection&lt;T&gt; Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 08d33725b47535fb3b88d2f8e653155e83ae5a57
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection&lt;T&gt; Návrhář aktivity
**RemoveFromCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity.  
  
## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection < T\> aktivity  
 <xref:System.Activities.Statements.RemoveFromCollection%601> Aktivity odebere určenou položku z konkrétní kolekce.  
  
### <a name="using-the-removefromcollectiont-activity-designer"></a>Pomocí RemoveFromCollection\<T > Návrhář aktivity  
 **RemoveFromCollection\<T >** Návrhář aktivity naleznete v **kolekce** kategorii **sada nástrojů**, který přistupuje kliknutím **Sada nástrojů** na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **RemoveFromCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, jako například uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.RemoveFromCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z RemoveFromCollection < Int32\>. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **RemoveFromCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.  
  
### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\> vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.RemoveFromCollection%601> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity. Výchozí hodnota je RemoveFromCollection < Int32\>.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Hodnota TRUE|Položka k přidání do **kolekce\<T >**. Tato položka je typu *T*, která je typu *TypeArgument*. Pokud chcete zadat položku, zadejte ve výrazu jazyka Visual Basic v tabulce vlastností.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Hodnota TRUE|Kolekce, do které by měla položka přidána. Tato kolekce je typu **ICollection < TypeArgument\>.** Chcete-li zadat kolekce, zadejte ve výrazu jazyka Visual Basic v tabulce vlastností.|  
|*TypeArgument*|Hodnota TRUE|Typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která označuje, zda zadaná položka byla odebrána z kolekce. Chcete-li zadat proměnnou pro vazbu na výsledek, zadejte v proměnné v tabulce vlastností|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)   
 [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)