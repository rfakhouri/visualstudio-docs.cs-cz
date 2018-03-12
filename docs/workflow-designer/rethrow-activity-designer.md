---
title: "Opětovné Návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b5650db4a140b216806f36239da955ee771cb8da
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="rethrow-activity-designer"></a>Opětovné Návrhář aktivity
**Opětovné** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Rethrow> aktivity.

## <a name="the-rethrow-activity"></a>Opětovné aktivity
 <xref:System.Activities.Statements.Rethrow> Aktivity vyvolá dříve vyvolaná výjimka. Tato aktivita lze použít pouze v <xref:System.Activities.Statements.Catch> obslužné rutiny v <xref:System.Activities.Statements.TryCatch> aktivity.

### <a name="using-the-rethrow-activity-designer"></a>Návrhář aktivity opětovné použití
 **Opětovné** Návrhář aktivity naleznete v **zpracování chyb** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Opětovné** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Rethrow> aktivitu výchozí **DisplayName** z Throw. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **opětovné** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-rethrow-properties"></a>Opětovné vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Rethrow> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Rethrow> aktivity. Výchozí hodnota je opětovné.|

## <a name="see-also"></a>Viz také

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)