---
title: RemoveFromCollection&lt;T&gt; Návrhář aktivity | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 45a426d4703ed2a402ee7f06341e55d65ae410ab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54784091"
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection&lt;T&gt; návrháře aktivit
**RemoveFromCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity.  
  
## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection\<T > aktivity  
 <xref:System.Activities.Statements.RemoveFromCollection%601> Aktivity Odebere zadanou položku z konkrétní kolekce.  
  
### <a name="using-the-removefromcollectiont-activity-designer"></a>Použití RemoveFromCollection\<T > návrháře aktivit  
 **RemoveFromCollection\<T >** návrháře aktivit najdete v **kolekce** kategorii **nástrojů**, který přistupuje po kliknutí **Nástrojů** kartě [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **RemoveFromCollection\<T >** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, jako například uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z RemoveFromCollection\<Int32 >. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **RemoveFromCollection\<T >** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností. V mřížce vlastností musí upravit další vlastnosti.  
  
### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection\<T > Vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.RemoveFromCollection%601> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity. Výchozí hodnota je RemoveFromCollection\<Int32 >.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Pravda|Položka k přidání do **kolekce\<T >**. Tato položka je typu *T*, která je typu *TypeArgument*. Chcete-li určit položku, zadejte výraz jazyka Visual Basic v mřížce vlastností.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Pravda|Kolekce, do kterého by měla položka přidána. Tato kolekce je typu **rozhraní ICollection\<TypeArgument >.** Chcete-li určit kolekci, zadejte výraz jazyka Visual Basic v mřížce vlastností.|  
|*TypeArgument*|Pravda|Typ položky obsažené v T <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* v poli se seznamem v mřížce vlastností.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která určuje, zda zadaná položka byla odebrána z kolekce. K určení proměnné vytvoření vazby mezi výsledkem, zadejte do proměnné v mřížce vlastností|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)   
 [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)