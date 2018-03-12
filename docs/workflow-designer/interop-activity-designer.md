---
title: "Návrhář aktivity spolupráce | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9ddc9cddbd8101932860bd2a2525186ff9ff36b6
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="interop-activity-designer"></a>Návrhář aktivity spolupráce
**Zprostředkovatel komunikace s objekty** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Interop> aktivity.

## <a name="the-interop-activity"></a>Spolupráce aktivity
 <xref:System.Activities.Statements.Interop> Aktivita řídí provádění typy, které jsou odvozeny od <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> v pracovním postupu.

### <a name="using-the-interop-activity-designer"></a>Pomocí návrháře spolupráce aktivity
 **Zprostředkovatel komunikace s objekty** Návrhář aktivity naleznete v **migrace** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 [Migrace](../workflow-designer/migration-activity-designers.md) kategorii, která obsahuje <xref:System.Activities.Statements.Interop> aktivita pouze se zobrazí v **sada nástrojů** Pokud projekt je cílení na celý [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)].

 Pro projekty C#, můžete určit cílovou znovu projekt, který používá celý [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] kliknutím pravým tlačítkem myši na projekt **Průzkumníku řešení** a výběrem **vlastnosti**. Na **aplikace** vyberte **NET Framework 4** možnost **cílové rozhraní**. Vyberte **Ano** v tlačítko **změnit cílový Framework** dialog, který zobrazí s žádostí o potvrzení této změny.

 U projektů jazyka Visual Basic, můžete určit cílovou znovu projekt, který používá celý [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] kliknutím pravým tlačítkem myši na projekt v **Průzkumníku řešení** a výběrem **vlastnosti**. Na **zkompilovat** , klikněte na **Upřesnit možnosti kompilace** tlačítko. Vyberte **rozhraní .net Framework 4** z **cílový framework seznam** a pak klikněte na **OK**. Klikněte na tlačítko **Ano** v tlačítko **změnit cílový Framework** dialog, který zobrazí s žádostí o potvrzení této změny.

 **Zprostředkovatel komunikace s objekty** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Interop> aktivitu výchozí **DisplayName** z zprostředkovatel komunikace s objekty. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **zprostředkovatel komunikace s objekty** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

 Klikněte **klikněte na tlačítko Procházet...**  textu v **ActivityType** pole, buď na **zprostředkovatel komunikace s objekty** aktivity návrháře nebo mřížku vlastností se zprovoznit **Procházet a vyberte .net zadejte** Dialogové okno. Jsou zobrazeny pouze typy pro pracovní postup 3.0 nebo aktivity pracovního postupu 3.5 (který je pouze typy odvozené od <xref:System.Workflow.ComponentModel.Activity>). Další informace o použití tohoto políčka a zadáním typu, najdete v článku [Procházet a vyberte typ dialogové okno .NET](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md) tématu.

### <a name="the-interop-properties"></a>Spolupráce vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Interop> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat vlastnosti mřížky nebo na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Interop> aktivity. Výchozí hodnota je zprostředkovatel komunikace s objekty. I když zobrazovaný název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|Určuje typ aktivity obsažených <xref:System.Activities.Statements.Interop> aktivity. Tento typ zadaný musí být odvozeny od <xref:System.Workflow.ComponentModel.Activity>.|

## <a name="see-also"></a>Viz také

- [Migrace](../workflow-designer/migration-activity-designers.md)