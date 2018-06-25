---
title: Návrhář postupu provádění – Návrhář aktivity Throw
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 71cf547a1ea3599de8926e40ca5a43f3bdea0f71
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758318"
---
# <a name="throw-activity-designer"></a>Návrhář aktivity Throw

**Throw** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Throw> aktivity.

## <a name="the-throw-activity"></a>Throw aktivity

<xref:System.Activities.Statements.Throw> Aktivity vyvolá výjimku.

### <a name="using-the-throw-activity-designer"></a>Pomocí návrháře aktivity Throw

Přístup **Throw** Návrhář aktivity v **zpracování chyb** kategorii **sada nástrojů**.

**Throw** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Throw> aktivitu výchozí **DisplayName** z Throw. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **Throw** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. <xref:System.Activities.Statements.Throw.Exception%2A> Vlastnost je nutné upravit na mřížku vlastností.

### <a name="the-throw-properties"></a>Vlastnosti Throw

Následující tabulce je zobrazena <xref:System.Activities.Statements.Throw> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Throw> aktivity. Výchozí hodnota je Throw.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|Hodnota TRUE|Výjimka, která má být vyvolána. Tato výjimka musí být odvozeny od <xref:System.Exception>. Pokud chcete zadat výjimku, zadejte výraz jazyka Visual Basic v tabulce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [opětovné](../workflow-designer/rethrow-activity-designer.md)
- [Návrhář aktivity Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)