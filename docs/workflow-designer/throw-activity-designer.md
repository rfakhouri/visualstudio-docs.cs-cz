---
title: Návrhář postupu provádění – Návrhář aktivity Throw
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7074ee2a11759983f103024033cb2b96322330cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434017"
---
# <a name="throw-activity-designer"></a>Návrhář aktivity Throw

**Throw** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Throw> aktivity.

## <a name="the-throw-activity"></a>Aktivity Throw

<xref:System.Activities.Statements.Throw> Aktivita vyvolá výjimku.

### <a name="using-the-throw-activity-designer"></a>Pomocí Návrhář aktivity Throw

Přístup **Throw** návrháře aktivit v **zpracování chyb** kategorii **nástrojů**.

**Throw** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Throw> aktivity s výchozím **DisplayName** o vyvolání výjimky. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **Throw** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. <xref:System.Activities.Statements.Throw.Exception%2A> Vlastnost musí upravit v mřížce vlastností.

### <a name="the-throw-properties"></a>Vyvolání vlastnosti

Následující tabulka ukazuje <xref:System.Activities.Statements.Throw> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.Throw> aktivity. Výchozí hodnota je vyvolání výjimky.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|Pravda|Výjimka, která má být vyvolána. Tato výjimka musí být odvozen od <xref:System.Exception>. Pokud chcete nastavit výjimky, zadejte výraz jazyka Visual Basic v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Rethrow](../workflow-designer/rethrow-activity-designer.md)
- [Návrhář aktivity Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)