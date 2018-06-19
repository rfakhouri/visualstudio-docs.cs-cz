---
title: Návrhář postupu provádění - vývojový diagram Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81af4a51da2bb15bafd17fc7ba98d676f7b0decc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974271"
---
# <a name="flowchart-activity-designer"></a>Vývojový diagram Návrhář aktivity

<xref:System.Activities.Statements.Flowchart> Aktivita se používá k vytváření pracovních postupů, které definovat a spravovat komplexní tok ovládací prvky. A <xref:System.Activities.Statements.Flowchart> může být vytvořené v kódu nebo pomocí návrháře pracovních postupů. Toto téma popisuje činnost návrháře pracovních postupů. Návrhář aktivity pracovního postupu Návrháře pracovního postupu systému Windows umožňuje vývojářům pro vytváření pracovních postupů přirozené způsobem.

## <a name="the-flowchart-activity"></a>Vývojový diagram aktivity

<xref:System.Activities.Statements.Flowchart> Určuje jedinečný <xref:System.Activities.Statements.Flowchart.StartNode%2A> který se spustí při spuštění pracovního postupu a používá síť propojení <xref:System.Activities.Statements.Flowchart.Nodes%2A> můžete vytvořit libovolný smyčky nebo přesměrovat tok na kdekoliv jinde v pracovním postupu provedení v daném okamžiku.

### <a name="using-the-flowchart-activity-designer"></a>Pomocí návrháře vývojový diagram aktivity

**Vývojový diagram** Návrhář aktivity naleznete v **vývojový diagram** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**kartě v Návrháři pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**Vývojový diagram** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na návrháře aktivit jsou obvykle umístěny, jako kořenové aktivity nebo jako podřízená jiné aktivity toku řízení. Pokud **vývojový diagram** Návrhář aktivity je vyřazeno na plochu návrháře pracovních postupů prázdné, vytvoří <xref:System.Activities.Statements.Flowchart> aktivity, který ve výchozím nastavení prezentuje v rozbalené zobrazení, ve kterém je počáteční uzel, který iniciuje provádění reprezentován jako zelená míč. Pokud **vývojový diagram** Návrhář aktivity je vyřazeno do další aktivity toku řízení, se prezentuje v minimalizovaném okně zobrazení, které lze rozšířit dvojitým kliknutím **vývojový diagram** Návrhář aktivity. Všechny aktivity v **sada nástrojů** může být přetažen přímo na **vývojový diagram** Návrhář aktivity, včetně další aktivity toku řízení.

Po přetahování různé návrháře aktivit na plátno návrháře pracovních postupů <xref:System.Activities.Activity> lze propojit objekty, které představují společně k určení pořadí zpracování. Pokud chcete vytvořit vazbu mezi aktivitou zdrojové a cílové aktivitě, myši nad návrháře zdrojové aktivity a odmocnina obslužné rutiny zobrazí na každé straně je. Klikněte na jednu z odmocnina obslužné rutiny a přetáhněte jej podržte tlačítko myši na jednu z obslužných rutin, které se zobrazí podobným způsobem kolem cílová aktivita, když ukazatele myši ho pomocí myši. Uvolnění tlačítka myši a vytvoří propojení mezi tyto dvě aktivity, které je reprezentována jako šipka z Návrháře zdrojové do cílové návrháře.

### <a name="flowchart-activity-properties"></a>Vývojový diagram vlastnosti aktivit

Následující tabulce je zobrazena <xref:System.Activities.Statements.Flowchart> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnost nebo na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje zobrazovaný název Návrhář aktivity v hlavičce. Výchozí hodnota je Vývojový diagram. Hodnotu lze upravit v **vlastnosti** okno nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Kolekce proměnných, které jsou určené v rámci to <xref:System.Activities.Statements.Flowchart> sdílet stavu ve jeho podřízené aktivity.|
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|<xref:System.Activities.Statements.FlowNode> Tedy spuštěna při <xref:System.Activities.Statements.Flowchart> spustí.|
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Obsahuje kolekci <xref:System.Activities.Statements.FlowNode> objekty v <xref:System.Activities.Statements.Flowchart>.|

## <a name="see-also"></a>Viz také

- [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)
- [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)