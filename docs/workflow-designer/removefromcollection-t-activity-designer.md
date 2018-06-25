---
title: Návrhář postupu provádění - RemoveFromCollection&lt;T&gt; Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53fc58e231e5ef1cbbc6106e279b4925d145dd9f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755934"
---
# <a name="removefromcollectiont-activity-designer"></a>RemoveFromCollection\<T > Návrhář aktivity

**RemoveFromCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity.

## <a name="the-removefromcollectiontactivity"></a>RemoveFromCollection\<T > aktivity

<xref:System.Activities.Statements.RemoveFromCollection%601> Aktivity odebere určenou položku z konkrétní kolekce.

### <a name="using-the-removefromcollectiont-activity-designer"></a>Pomocí RemoveFromCollection\<T > Návrhář aktivity

Přístup **RemoveFromCollection\<T >** Návrhář aktivity v **kolekce** kategorii **sada nástrojů**. **RemoveFromCollection\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a bez ohledu na aktivity jsou obvykle umístěny, jako například vyřadit na povrch Návrhář postupu provádění uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.RemoveFromCollection%601> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z RemoveFromCollection < Int32\>. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **RemoveFromCollection < T\>**  Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. Ostatní vlastnosti musí být upravit na mřížku vlastností.

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\> vlastnosti

Následující tabulce je zobrazena <xref:System.Activities.Statements.RemoveFromCollection%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.RemoveFromCollection%601> aktivity. Výchozí hodnota je RemoveFromCollection < Int32\>.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Hodnota TRUE|Položka k přidání do **kolekce\<T >**. Tato položka je typu *T*, která je typu *TypeArgument*. Pokud chcete zadat položku, zadejte ve výrazu jazyka Visual Basic v tabulce vlastností.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Hodnota TRUE|Kolekce, do které by měla položka přidána. Tato kolekce je typu **ICollection < TypeArgument\>.** Chcete-li zadat kolekce, zadejte ve výrazu jazyka Visual Basic v tabulce vlastností.|
|*TypeArgument*|Hodnota TRUE|Typ T položek, které jsou součástí <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* do pole se seznamem v tabulce vlastností.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Hodnota, která označuje, zda zadaná položka byla odebrána z kolekce. Chcete-li zadat proměnnou pro vazbu na výsledek, zadejte v proměnné v tabulce vlastností|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)