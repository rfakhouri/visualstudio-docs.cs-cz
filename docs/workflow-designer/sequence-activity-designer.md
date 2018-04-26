---
title: Návrhář postupu provádění – Návrhář aktivity pořadí
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e72c5b5e43ca037a6d65e3e4980fdb0f89f000f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sequence-activity-designer"></a>Návrhář aktivity pořadí

<xref:System.Activities.Statements.Sequence> Aktivity obsahuje uspořádanou kolekci podřízené aktivity, které se provede v pořadí.

Jiný způsob, jak spustit sadu aktivit, aby se má používat <xref:System.Activities.Statements.Flowchart> aktivity. Zvažte použití [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) Pokud máte jednoduchý vytvoření větve nebo opakování ve smyčce toku programu, který chcete diagramem modelu.

## <a name="using-the-sequence-activity-designer"></a>Pomocí návrháře pořadí aktivity

Chcete-li přidat <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte **pořadí** Návrhář aktivity z **sada nástrojů** a umístěte jej na povrch Návrháře pracovního postupu systému Windows. Přidání podřízené aktivity k tomuto <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte některé aktivity z **sada nástrojů** a umístěte jej na trojúhelníček do pole s textem pomocný parametr "Sem umístěte aktivity".

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Vlastnosti aktivity pořadí v Návrháři pracovních postupů

Následující tabulce je zobrazena <xref:System.Activities.Statements.Sequence> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnost nebo na plochu návrháře.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Sequence> Návrhář aktivity v hlavičce. Výchozí hodnota je pořadí. Hodnota se dá upravit v mřížku vlastností, nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|

## <a name="see-also"></a>Viz také

- [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)