---
title: ExistsInCollection&lt;T&gt; Návrhář aktivity | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 263bbf16c72bab5a42dc0ba1465d4c7062333071
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62952824"
---
# <a name="existsincollectionlttgt-activity-designer"></a>ExistsInCollection&lt;T&gt; návrháře aktivit
**ExistsInCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.ExistsInCollection%601> aktivity.  
  
## <a name="the-existsincollectiont-activity"></a>ExistsInCollection\<T > aktivity  
 <xref:System.Activities.Statements.ExistsInCollection%601> Aktivit Určuje, zda zadaná položka existuje v konkrétní kolekci.  
  
### <a name="using-the-existsincollectiont-activity-designer"></a>Použití ExistsInCollection\<T > návrháře aktivit  
 **ExistsInCollection\<T >** návrháře aktivit najdete v **kolekce** kategorii **nástrojů**, který přistupuje po kliknutí  **Panel nástrojů** kartě [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **ExistsInCollection\<T >** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, jako například uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.ExistsInCollection%601> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z ExistsInCollection\<Int32 >. (Ve výchozím nastavení, *TypeArgument* je **Int32**. Lze jej změnit v mřížce vlastností.)  <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **ExistsInCollection\<T >** Návrhář aktivity nebo **DisplayName** pole mřížku vlastností. V mřížce vlastností musí upravit další vlastnosti.  
  
### <a name="the-existsincollectiont-properties"></a>ExistsInCollection\<T > Vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.ExistsInCollection%601> vlastnosti a popisuje, jak se používají v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.ExistsInCollection%601> aktivity. Výchozí hodnota je ExistsInCollection\<Int32 >. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|Pravda|Položka k přidání do kolekce\<T >. Tato položka je typu *T* je typu *TypeArgument*. Chcete-li určit položku, zadejte výraz jazyka Visual Basic v mřížce vlastností.|  
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|Pravda|Kolekce, do kterého by měla položka přidána. Tato kolekce je typu **rozhraní ICollection\<TypeArgument >.** Chcete-li určit kolekci, zadejte výraz jazyka Visual Basic v mřížce vlastností.|  
|*TypeArgument*|Pravda|Typ položky obsažené v T <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* v poli se seznamem v mřížce vlastností.|  
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která označuje, zda zadaná položka existuje v kolekci. K určení proměnné vytvoření vazby mezi výsledkem, zadejte proměnnou jazyka Visual Basic v mřížce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Kolekce](../workflow-designer/collection-activity-designers.md)   
 [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)   
 [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)   
 [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)