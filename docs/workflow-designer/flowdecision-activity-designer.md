---
title: Návrhář postupu provádění - FlowDecision Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.FlowDecision.UI
ms.assetid: 4a49edc3-3662-4b7b-812e-0a5ba00d6c94
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08c8aadb3c452a59f1b44cd030331164384d23bb
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758334"
---
# <a name="flowdecision-activity-designer"></a>Návrhář aktivity FlowDecision

<xref:System.Activities.Statements.FlowDecision> Uzel je podmíněného uzel, který poskytuje větev pro tok řízení do jedné ze dvou alternativy založené na tom, jestli splňuje zadanou podmínku. Pokud toku vyžaduje více než dvě větve, použijte <xref:System.Activities.Statements.FlowSwitch%601> místo.

## <a name="the-flowdecision-node"></a>Uzel FlowDecision

Použití <xref:System.Activities.Statements.FlowDecision> při toku můžete vytvořit větve do dvě cesty. A <xref:System.Activities.Statements.FlowDecision> má uzel <xref:System.Activities.Statements.FlowDecision.Condition%2A> a <xref:System.Activities.Statements.FlowNode> související s jednotlivými dvě možné výsledky: <xref:System.Activities.Statements.FlowDecision.True%2A> nebo <xref:System.Activities.Statements.FlowDecision.False%2A>. <xref:System.Activities.Statements.FlowDecision.Condition%2A> Je vyhodnocena a další určuje hodnota atributu toto testování <xref:System.Activities.Statements.FlowNode> ke zpracování v rámci <xref:System.Activities.Statements.Flowchart>.

### <a name="using-the-flowdecision-designer"></a>Pomocí návrháře FlowDecision

**FlowDecision** designer naleznete v **vývojový diagram** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů** Karta v Návrháři pracovních postupů. Případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky, nebo klikněte na tlačítko **Ctrl**+**Alt** + **X**.

**FlowDecision** designer můžete přetáhnout z **sada nástrojů** a vyřadit na povrch v Návrháři pracovních postupů **vývojový diagram** Návrhář aktivity. Tím se vytvoří <xref:System.Activities.Statements.FlowDecision> s názvem bez přípony **rozhodnutí** v rámci <xref:System.Activities.Statements.Flowchart> aktivity. Myši nad návrháře a **True** a **False** zobrazí čtvereček obslužné rutiny pro dvě větve.

Po přetahování **FlowDecision** designer a jinými návrháři na **vývojový diagram**, může být propojený uzly společně k určení pořadí zpracování. Chcete-li vytvořit vazbu mezi zdrojový uzel (včetně **True** a **False** větví z **FlowDecision**) a cílový uzel myši nad návrháře zdrojový uzel a odmocnina popisovače zobrazí na každé straně ho. Klikněte na jednu z odmocnina obslužné rutiny a přetáhněte jej podržte tlačítko myši na jednu z obslužných rutin, které se zobrazí podobným způsobem kolem cílový uzel, když jste myší. Uvolnění tlačítka myši a vytvoří se mezi propojení tyto dva uzly, které je reprezentována jako šipka z Návrháře zdroje návrháře cílový.

Výraz, který stavy <xref:System.Activities.Statements.FlowDecision.Condition%2A> lze napsat **podmínku** pole **vlastnosti** okno kliknutím, kde text nápovědy říká "Zadejte výraz jazyka Visual Basic".

### <a name="the-flowdecision-properties"></a>Vlastnosti FlowDecision

Následující tabulce je zobrazena <xref:System.Activities.Statements.FlowDecision> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v tabulce vlastností nebo na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.FlowDecision.Condition%2A>|Hodnota TRUE|Podmínku, která určuje, které cesty přebírá řízení toku.|
|<xref:System.Activities.Statements.FlowDecision.True%2A>|False|Cesta provedenou řízení toku, pokud <xref:System.Activities.Statements.FlowDecision.Condition%2A> je splněna.|
|<xref:System.Activities.Statements.FlowDecision.False%2A>|False|Cesta provedenou řízení toku, pokud <xref:System.Activities.Statements.FlowDecision.Condition%2A> není splněna.|

## <a name="see-also"></a>Viz také:

- [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)
- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)