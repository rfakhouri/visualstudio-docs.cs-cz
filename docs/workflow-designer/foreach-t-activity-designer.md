---
title: ForEach&lt;T&gt; Návrhář aktivity | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a9f62f8b3fcb96d0d0abc8ba52b2d0ccfb42473
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt; Návrhář aktivity
<xref:System.Activities.Statements.ForEach%601> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.ForEach%601.Body%2A> pro každou položku v zadané <xref:System.Activities.Statements.ForEach%601.Values%2A> kolekce.

## <a name="foreacht-properties-in-the-workflow-designer"></a>Foreach – < T\> vlastnosti v Návrháři pracovních postupů
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.ForEach%601> vlastnosti aktivity a popisuje, jak je používat v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.ForEach%601> aktivity. Výchozí hodnota je ForEach < Int32\>. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|Hodnota TRUE|Kolekce položek, které mají iterace. Chcete-li nastavit <xref:System.Activities.Statements.ForEach%601.Values%2A>, zadejte [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výrazu v **hodnoty** pole na **ForEach < T\>**  aktivity návrháře nebo v tabulce vlastností.|
|*TypeArgument*|Hodnota TRUE|Typ položky v <xref:System.Activities.Statements.ForEach%601.Values%2A> kolekce určeného obecný parametr *T*. Ve výchozím nastavení *TypeArgument* je nastaven na **Int32**. Chcete-li změnit typ, změňte hodnotu *TypeArgument* – pole se seznamem v tabulce vlastností.|

 Ve výchozím nastavení, iterace smyčky jmenuje **položky**. Můžete změnit název proměnné iterator v <xref:System.Activities.Statements.ForEach%601> Návrhář aktivity. Iterator smyčky lze použít ve výrazech v podřízených prvků <xref:System.Activities.Statements.ForEach%601> aktivity.

## <a name="see-also"></a>Viz také

- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)