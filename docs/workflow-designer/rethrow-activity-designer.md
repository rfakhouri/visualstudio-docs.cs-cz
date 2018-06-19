---
title: Návrhář postupu provádění - opětovné Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d441724afa1cf481bc15e2a43e6ec744a951187
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973833"
---
# <a name="rethrow-activity-designer"></a>Opětovné Návrhář aktivity

**Opětovné** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Rethrow> aktivity.

## <a name="the-rethrow-activity"></a>Opětovné aktivity
 <xref:System.Activities.Statements.Rethrow> Aktivity vyvolá dříve vyvolaná výjimka. Tato aktivita lze použít pouze v <xref:System.Activities.Statements.Catch> obslužné rutiny v <xref:System.Activities.Statements.TryCatch> aktivity.

### <a name="using-the-rethrow-activity-designer"></a>Návrhář aktivity opětovné použití
 **Opětovné** Návrhář aktivity naleznete v **zpracování chyb** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně návrháře pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Opětovné** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Rethrow> aktivitu výchozí **DisplayName** z Throw. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **opětovné** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-rethrow-properties"></a>Opětovné vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Rethrow> vlastnosti a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.Rethrow> aktivity. Výchozí hodnota je opětovné.|

## <a name="see-also"></a>Viz také

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)