---
title: Návrhář postupu provádění – ForEach&lt;T&gt; návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e441898973614b6e3e33fc91d5d9688b51aab7fe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949614"
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt; návrháře aktivit

<xref:System.Activities.Statements.ForEach%601> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.ForEach%601.Body%2A> pro každou položku v zadané <xref:System.Activities.Statements.ForEach%601.Values%2A> kolekce.

## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach < T\> vlastnosti v Návrháři postupu provádění

V následující tabulce jsou uvedeny nejužitečnější <xref:System.Activities.Statements.ForEach%601> vlastnosti aktivit a popisuje, jak je používat v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.ForEach%601> aktivity. Výchozí hodnota je ForEach < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|Pravda|Kolekce položek, které chcete iterovat. Chcete-li nastavit <xref:System.Activities.Statements.ForEach%601.Values%2A>, zadejte výraz jazyka Visual Basic v **hodnoty** pole na **ForEach < T\>**  aktivity návrháře nebo v mřížce vlastností.|
|*TypeArgument*|Pravda|Typ položky v <xref:System.Activities.Statements.ForEach%601.Values%2A> kolekci specifikované souborem obecný parametr *T*. Ve výchozím nastavení *TypeArgument* je nastavena na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* – pole se seznamem v mřížce vlastností.|

Ve výchozím nastavení, iterace smyčky název **položky**. Můžete změnit název proměnné iterátoru v <xref:System.Activities.Statements.ForEach%601> návrháře aktivit. Iterace smyčky můžete použít ve výrazech v podřízených položek <xref:System.Activities.Statements.ForEach%601> aktivity.

## <a name="see-also"></a>Viz také:

- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)