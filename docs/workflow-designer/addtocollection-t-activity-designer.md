---
title: Návrhář postupu provádění - AddToCollection<T> návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.AddToCollection`1.UI
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7e339e2639d85f89d4110c36710ab9c19e0fe333
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842082"
---
# <a name="addtocollectiont-activity-designer"></a>AddToCollection\<T > návrháře aktivit

**AddToCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.AddToCollection%601> aktivity.

## <a name="the-addtocollectiont-activity"></a>AddToCollection\<T > aktivity

<xref:System.Activities.Statements.AddToCollection%601> Aktivita přidá položku do kolekce.

### <a name="using-the-addtocollectiont-activity-designer"></a>Použití AddToCollection\<T > návrháře aktivit

**AddToCollection\<T >** návrháře aktivit najdete v **kolekce** kategorii **nástrojů**, který přistupuje po kliknutí  **Panel nástrojů** kartu návrháře postupu provádění. Můžete také vybrat **nástrojů** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Alt** + **X**.

**AddToCollection\<T >** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou umístěny, například jako v <xref:System.Activities.Statements.Sequence>. Vyřazení **AddToCollection\<T >** vytvoří Návrhář aktivity <xref:System.Activities.Statements.AddToCollection%601> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z AddToCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. TypeArgument lze změnit v mřížce vlastností.) <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **AddToCollection < T\>**  Návrhář aktivity nebo **DisplayName** pole mřížku vlastností. V mřížce vlastností musí upravit další vlastnosti.

### <a name="the-addtocollectiont-properties"></a>AddToCollection\<T > Vlastnosti

Následující tabulka ukazuje <xref:System.Activities.Statements.AddToCollection%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.AddToCollection%601> aktivity. Výchozí hodnota je AddToCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|Pravda|Položka k přidání do kolekce\<T >. Tato položka je typu *T*, která je typu *TypeArgument*. Chcete-li určit položku, zadejte výraz jazyka Visual Basic v mřížce vlastností.|
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|Pravda|Kolekce, do kterého by měla položka přidána. Tato kolekce je typu **rozhraní ICollection < TypeArgument\>**. Chcete-li určit kolekci, zadejte výraz jazyka Visual Basic v mřížce vlastností.|
|*TypeArgument*|Pravda|Typ položky obsažené v T <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* v poli se seznamem v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T > návrháře aktivit](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)