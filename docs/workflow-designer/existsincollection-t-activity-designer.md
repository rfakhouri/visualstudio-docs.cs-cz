---
title: Návrhář postupu provádění - ExistsInCollection&lt;T&gt; Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c5625f42489752647da57fad9956cff8c64b8f5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974397"
---
# <a name="existsincollectiont-activity-designer"></a>ExistsInCollection\<T > Návrhář aktivity

**ExistsInCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.ExistsInCollection%601> aktivity.

## <a name="the-existsincollectiont-activity"></a>ExistsInCollection\<T > aktivity
 <xref:System.Activities.Statements.ExistsInCollection%601> Aktivity Určuje, zda zadaná položka existuje v určité kolekci.

### <a name="using-the-existsincollectiont-activity-designer"></a>Pomocí ExistsInCollection\<T > Návrhář aktivity
 **ExistsInCollection\<T >** Návrhář aktivity naleznete v **kolekce** kategorii **sada nástrojů**, což je dostat kliknutím  **Sada nástrojů** karta Návrháře pracovního postupu (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **ExistsInCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.ExistsInCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z ExistsInCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. Ho můžete změnit v tabulce vlastností.)  <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **ExistsInCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.

### <a name="the-existsincollectiont-properties"></a>ExistsInCollection\<T > Vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.ExistsInCollection%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.ExistsInCollection%601> aktivity. Výchozí hodnota je ExistsInCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|Hodnota TRUE|Položka k přidání do kolekce\<T >. Tato položka je typu *T* je typu *TypeArgument*. Pokud chcete zadat položku, zadejte výraz jazyka Visual Basic v tabulce vlastností.|
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|Hodnota TRUE|Kolekce, do které by měla položka přidána. Tato kolekce je typu **ICollection < TypeArgument\>.** Pokud chcete zadat kolekce, zadejte výraz jazyka Visual Basic v tabulce vlastností.|
|*TypeArgument*|Hodnota TRUE|Typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která označuje, zda zadaná položka existuje v kolekci. Pokud chcete zadat proměnnou pro vazbu na výsledek, zadejte proměnnou jazyka Visual Basic v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)