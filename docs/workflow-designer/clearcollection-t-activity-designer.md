---
title: Návrhář postupu provádění - ClearCollection<T> návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cab7ea023524da7e28e2baa2d4e5018cd091c60d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949991"
---
# <a name="clearcollectiont-activity-designer"></a>ClearCollection\<T > návrháře aktivit

**ClearCollection\<T >** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.ClearCollection%601> aktivity.

## <a name="the-clearcollectiont-activity"></a>ClearCollection\<T > aktivity

<xref:System.Activities.Statements.ClearCollection%601> Aktivity vymaže kolekce všech položek.

### <a name="using-the-clearcollectiont-activity-designer"></a>Použití ClearCollection\<T > návrháře aktivit

**ClearCollection\<T >** návrháře aktivit najdete v **kolekce** kategorii **nástrojů**, který přistupuje po kliknutí  **Panel nástrojů** kartu návrháře postupu provádění. Můžete také vybrat **nástrojů** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Alt** + **X**.

**ClearCollection\<T >** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou umístěny, například jako v <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.ClearCollection%601> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z ClearCollection < Int32\>. (Ve výchozím nastavení, *TypeArgument* je **Int32**. TypeArgument lze změnit v mřížce vlastností.) <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **ClearCollection < T\>**  Návrhář aktivity nebo **DisplayName** pole mřížku vlastností. V mřížce vlastností musí upravit další vlastnosti.

### <a name="the-clearcollectiont-properties"></a>ClearCollection\<T > Vlastnosti

Následující tabulka ukazuje <xref:System.Activities.Statements.ClearCollection%601> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.ClearCollection%601> aktivity. Výchozí hodnota je ClearCollection < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|Pravda|Určuje kolekci, která vymažou položek. Tato kolekce je typu **rozhraní ICollection\<TypeArgument >.** Chcete-li určit kolekci, zadejte výraz jazyka Visual Basic v mřížce vlastností.|
|*TypeArgument*|Pravda|Určuje typ položky obsažené v T <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení to *TypeArgument* je typ nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* v poli se seznamem v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)