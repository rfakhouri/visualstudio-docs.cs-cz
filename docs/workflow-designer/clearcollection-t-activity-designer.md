---
title: "ClearCollection&lt;T&gt; Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 54cac37194a3b96d464b886c14bfbbbde4a1f861
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="clearcollectionlttgt-activity-designer"></a>ClearCollection&lt;T&gt; Návrhář aktivity
**ClearCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.ClearCollection%601> aktivity.  
  
## <a name="the-clearcollectiont-activity"></a>ClearCollection < T\> aktivity  
 <xref:System.Activities.Statements.ClearCollection%601> Aktivity vymaže kolekce všech položek.  
  
### <a name="using-the-clearcollectiont-activity-designer"></a>Pomocí ClearCollection\<T > Návrhář aktivity  
 **ClearCollection\<T >** Návrhář aktivity naleznete v **kolekce** kategorii **sada nástrojů**, což je dostat kliknutím  **Sada nástrojů** kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **ClearCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.ClearCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z ClearCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. To lze změnit v tabulce vlastností.) <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **ClearCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.  
  
### <a name="the-clearcollectiont-properties"></a>ClearCollection < T\> vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.ClearCollection%601> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.ClearCollection%601> aktivity. Výchozí hodnota je ClearCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|Hodnota TRUE|Určuje kolekci, která ji vymazat z položek. Tato kolekce je typu **ICollection\<TypeArgument >.** Pokud chcete zadat kolekce, zadejte výraz jazyka Visual Basic v tabulce vlastností.|  
|*TypeArgument*|Hodnota TRUE|Určuje typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)   
 [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)