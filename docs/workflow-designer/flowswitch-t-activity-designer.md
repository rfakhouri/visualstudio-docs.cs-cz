---
title: FlowSwitch&lt;T&gt; Návrhář aktivity | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb8c28f835fad4e70b213d13aaeb654780b72297
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="flowswitchlttgt-activity-designer"></a>FlowSwitch&lt;T&gt; Návrhář aktivity
<xref:System.Activities.Statements.FlowSwitch%601> Aktivita je podmíněného uzel, který poskytuje vytvoření větve pro tok řízení podle kritérium přiřazování, pokud je potřeba víc než dva alternativní větve. Pokud postup vytvoření větve vyžaduje pouze dvě cesty, použijte <xref:System.Activities.Statements.FlowDecision> aktivity místo.

## <a name="the-flowswitcht-activity"></a>FlowSwitch < T\> aktivity
 <xref:System.Activities.Statements.FlowSwitch%601> Obsahuje aktivitu <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> , vrátí hodnotu typu *T* (určeného vlastností obecný parametr) vyhodnocena. Aktivita také obsahuje sadu <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>, která určuje jedinečný mapování z možných výsledky tohoto hodnocení na sadu <xref:System.Activities.Statements.FlowNode> objekty. <xref:System.Activities.Statements.FlowNode> Provést, je ten, jehož objektu typu *T* odpovídá hodnotě vyhodnotí <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. A <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> případ lze zadat (volitelně) pro případ, ve kterém se získávají žádná shoda.

### <a name="using-the-flowswitcht-activity-designer"></a>Pomocí FlowSwitch\<T > Návrhář aktivity
 **FlowSwitch\<T >** Návrhář aktivity naleznete v **vývojový diagram** kategorii **sada nástrojů**, což je dostat kliknutím **Sada nástrojů** karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **FlowSwitch\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor v rámci **vývojový diagram** Návrhář aktivity. Použití **vyberte typy** okně, které se zobrazí k určení typu (související v kódu pomocí <xref:System.Activities.Statements.FlowSwitch%601> podle jeho obecný parametr) získané z vyhodnocení <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. Tento postup vytvoří <xref:System.Activities.Statements.FlowSwitch%601> aktivity s názvem bez přípony **přepínač** v rámci <xref:System.Activities.Statements.Flowchart> aktivity. <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> Lze napsat **výraz** pole **vlastnosti** okno kliknutím, kde text nápovědy říká "Zadejte výraz jazyka Visual Basic".

 Ukazatele myši **FlowSwitch\<T >** Návrhář aktivity způsobí odmocnina obslužných rutin, které se používají k propojte <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> zobrazí jeho okrajů. Po přetahování **FlowSwitch < T\>**  Návrhář aktivity a dalších návrháře aktivit do **vývojový diagram**, <xref:System.Activities.Activity> objekty, které představují připraveni spojeno Chcete-li určit pořadí zpracování. K vytvoření jednoho z <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> přidružené <xref:System.Activities.Statements.FlowSwitch%601>, klikněte na jednu z čtvercovou případu obslužné rutiny na obvodu **FlowSwitch < T\>**  a přetáhněte ji na jeden z obslužné rutiny pro zpracování (tím, že se tlačítko myši) která se zobrazí podobným způsobem kolem cílová aktivita, když ukazatel myši setrvá jeho designer. Uvolnění tlačítka myši a z šipka **FlowSwitch < T\>**  do cílové návrháře se zobrazí představující tento případ. Výchozí hodnota pro tento případ se zobrazí na šipku a lze ho upravovat v **případ** pole **vlastnosti** okno.

### <a name="the-flowswitcht-properties"></a>FlowSwitch < T\> vlastnosti
 Následující tabulce je zobrazena <xref:System.Activities.Statements.FlowSwitch%601> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v tabulce vlastností nebo na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|Hodnota TRUE|Určuje výraz, který se vyhodnotí k určení, které <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> přepnout v cestě k provádění.|
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|Určuje jedinečný mapování z možných výsledků získaných z vyhodnocení <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> na sadu <xref:System.Activities.Statements.FlowNode> objekty.|
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|Hodnota TRUE|Určuje mapování při vyhodnocení <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> neodpovídá jednu z hodnot, které jsou součástí <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> objektu.|

## <a name="see-also"></a>Viz také

- [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)
- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)