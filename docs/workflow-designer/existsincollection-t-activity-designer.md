---
title: "ExistsInCollection&lt;T&gt; Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: bcd3028335ed48f4eba8c647f124d0d537deaf3c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="existsincollectionlttgt-activity-designer"></a>ExistsInCollection&lt;T&gt; Návrhář aktivity
**ExistsInCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.ExistsInCollection%601> aktivity.  
  
## <a name="the-existsincollectiont-activity"></a>ExistsInCollection < T\> aktivity  
 <xref:System.Activities.Statements.ExistsInCollection%601> Aktivity Určuje, zda zadaná položka existuje v určité kolekci.  
  
### <a name="using-the-existsincollectiont-activity-designer"></a>Pomocí ExistsInCollection\<T > Návrhář aktivity  
 **ExistsInCollection\<T >** Návrhář aktivity naleznete v **kolekce** kategorii **sada nástrojů**, což je dostat kliknutím  **Sada nástrojů** kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **ExistsInCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, jako například uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.ExistsInCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z ExistsInCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. Ho můžete změnit v tabulce vlastností.)  <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **ExistsInCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.  
  
### <a name="the-existsincollectiont-properties"></a>ExistsInCollection < T\> vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.ExistsInCollection%601> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.ExistsInCollection%601> aktivity. Výchozí hodnota je ExistsInCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|Hodnota TRUE|Položka k přidání do kolekce\<T >. Tato položka je typu *T* je typu *TypeArgument*. Pokud chcete zadat položku, zadejte výraz jazyka Visual Basic v tabulce vlastností.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|Hodnota TRUE|Kolekce, do které by měla položka přidána. Tato kolekce je typu **ICollection < TypeArgument\>.** Pokud chcete zadat kolekce, zadejte výraz jazyka Visual Basic v tabulce vlastností.|  
|*TypeArgument*|Hodnota TRUE|Typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která označuje, zda zadaná položka existuje v kolekci. Pokud chcete zadat proměnnou pro vazbu na výsledek, zadejte proměnnou jazyka Visual Basic v tabulce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)   
 [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)