---
title: "Throw – Návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e0b41fb8fcbbb80f2f99558f07c5e5a4f9e4a85b
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="throw-activity-designer"></a>Throw – Návrhář aktivity
**Throw** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Throw> aktivity.

## <a name="the-throw-activity"></a>Throw aktivity
 <xref:System.Activities.Statements.Throw> Aktivity vyvolá výjimku.

### <a name="using-the-throw-activity-designer"></a>Pomocí návrháře aktivity Throw
 **Throw** Návrhář aktivity naleznete v **zpracování chyb** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Throw** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Throw> aktivitu výchozí **DisplayName** z Throw. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **Throw** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností. <xref:System.Activities.Statements.Throw.Exception%2A> Vlastnost je nutné upravit na mřížku vlastností.

### <a name="the-throw-properties"></a>Vlastnosti Throw
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Throw> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Throw> aktivity. Výchozí hodnota je Throw.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|Výjimka, která má být vyvolána. Tato výjimka musí být odvozeny od <xref:System.Exception>. Pokud chcete zadat výjimku, zadejte výraz jazyka Visual Basic v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [opětovné](../workflow-designer/rethrow-activity-designer.md)
- [Návrhář aktivity Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)