---
title: AddToCollection&lt;T&gt; Návrhář aktivity | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.AddToCollection`1.UI
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c961c8ab893b1d8b4a2d519d8b9dce27fd6f93c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="addtocollectionlttgt-activity-designer"></a>AddToCollection&lt;T&gt; Návrhář aktivity
**AddToCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.AddToCollection%601> aktivity.

## <a name="the-addtocollectiont-activity"></a>AddToCollection < T\> aktivity
 <xref:System.Activities.Statements.AddToCollection%601> Aktivita přidá položku do kolekce.

### <a name="using-the-addtocollectiont-activity-designer"></a>Pomocí AddToCollection\<T > Návrhář aktivity
 **AddToCollection\<T >** Návrhář aktivity naleznete v **kolekce** kategorii **sada nástrojů**, což je dostat kliknutím  **Sada nástrojů** kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **AddToCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.AddToCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z AddToCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. To lze změnit v tabulce vlastností.) <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **AddToCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.

### <a name="the-addtocollectiont-properties"></a>AddToCollection < T\> vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.AddToCollection%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.AddToCollection%601> aktivity. Výchozí hodnota je AddToCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|Hodnota TRUE|Položka k přidání do kolekce\<T >. Tato položka je typu *T*, která je typu *TypeArgument*. Pokud chcete zadat položku, zadejte ve výrazu jazyka Visual Basic v tabulce vlastností.|
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|Hodnota TRUE|Kolekce, do které by měla položka přidána. Tato kolekce je typu **ICollection < TypeArgument\>**. Pokud chcete zadat kolekce, zadejte výraz jazyka Visual Basic v tabulce vlastností.|
|*TypeArgument*|Hodnota TRUE|Typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T > Návrhář aktivity](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)