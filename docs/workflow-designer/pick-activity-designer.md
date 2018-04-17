---
title: Vyberte Návrhář aktivity | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Pick.UI
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4c9528d46d43441333723ba67f324ca46929eb38
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="pick-activity-designer"></a>Vyberte Návrhář aktivity
<xref:System.Activities.Statements.Pick> Poskytuje aktivity toku řízení na základě událostí. Aktivity spustí jeden z několika větve v reakci na aktivační událost.

## <a name="the-pick-activity"></a>Vybrat aktivitu
 A <xref:System.Activities.Statements.Pick> aktivity obsahuje kolekci <xref:System.Activities.Statements.PickBranch> objekty, z nichž jeden <xref:System.Activities.Statements.Pick> aktivity můžete spustit z důvodu některých příchozí události, která slouží jako aktivační událost. Tímto způsobem Návrhář pracovního postupu systému Windows umožňuje modelování toku řízení na základě událostí. Každý <xref:System.Activities.Statements.PickBranch> obsahuje <xref:System.Activities.Statements.PickBranch.Trigger%2A> a <xref:System.Activities.Statements.PickBranch.Action%2A>. Na začátku <xref:System.Activities.Statements.Pick> provádění aktivity, všechny aktivační události aktivity <xref:System.Activities.Statements.PickBranch> elementy jsou naplánovány. Po dokončení první aktivitu, bude odpovídající aktivita akce je naplánováno a všechny ostatní aktivity aktivační události došlo ke zrušení.

### <a name="how-to-use-the-pick-activity-designer"></a>Jak používat návrháře vyberte aktivity
 **Vyberte** Návrhář aktivity naleznete v **tok řízení** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Vyberte** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli návrháře aktivit jsou obvykle umístěny, například uvnitř  **Pořadí** Návrhář aktivity. Po vyřazení do [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], vytvoří <xref:System.Activities.Statements.Pick> aktivity, který ve výchozím nastavení obsahuje dvě prázdný <xref:System.Activities.Statements.PickBranch> aktivitám v podobě elementů pomocí zobrazení názvů pobočka1 a Branch2. Tyto příslušných <xref:System.Activities.Statements.PickBranch.DisplayName%2A> hodnoty vlastností lze upravit v **PickBranch** návrháře hlavičky aktivity nebo uvnitř **vlastnosti** okna pro každou větev.

 Existují dva způsoby, jak přidat <xref:System.Activities.Statements.PickBranch> aktivity do kolekce <xref:System.Activities.Statements.Pick> objektu: přetahování a vkládání **PickBranch** návrháře z **sada nástrojů** nebo pomocí místní nabídky z v rámci **vyberte** návrhovou plochu. Podrobnosti najdete v tématu [PickBranch](../workflow-designer/pickbranch-activity-designer.md) tématu. Všimněte si, že se za jedinou položku, která může být umístěna uvnitř **vyberte** je Návrhář aktivity **PickBranch** Návrhář aktivity.

### <a name="pick-activity-properties-in-the-workflow-designer"></a>Vyberte vlastnosti aktivity v Návrháři pracovních postupů
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Pick> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnost nebo na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Pick> Návrhář aktivity v hlavičce. Výchozí hodnota je vybrat. Hodnota se dá upravit v mřížku vlastností, nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|

## <a name="see-also"></a>Viz také

- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)
- [Výběr aktivity](/dotnet/framework/windows-workflow-foundation/pick-activity)
- [Použití aktivity Pick](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)